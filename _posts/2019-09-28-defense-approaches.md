---
title: 'Adversarial Defenses Survey'
id: 4
excerpt: A review of existing approaches to defense against adversarial examples. 
date: 2019-09-38
permalink: /posts/2019/08/adversarial-defenses/
tags:
  - adversarial_learning
---

I was recently asked what approaches, of the many present in literature, I would prioritize if I personally were implementing a product or system to defend against adversarial attacks on machine learning models. I thought it was such an interesting question that it was worth writing about.

## Evaluation Framework

In order to evaluate adversarial training defenses consistently, we must define the characteristics of defensive methods that will influence whether or not they are selected for recommendation. The most obvious of these is efficacy: does the method improve robustness against adversarial training, and to what extent? Note that the performance gain will in all cases depend on the context; some methods outperform the others on some datasets, but underperform them on others. Another consideration is the impact on the existing system. The implementation work may include not only engineering effort but also processes like additional data labeling, if necessary. Runtime and computational burden is also a concern. Because a method that is included in the product will ultimately be customer-facing, in a system designed to build trust in machine learning systems, we also consider the interpretability of the method. These pillars will thus provide the framework used to compare and select approaches from published adversarial learning defenses.

## Survey of Defense Approaches

### Dataset Augmentation

The most common and intuitive defense against adversarial examples is adversarial training. In particular, _ensemble adversarial training_ [1] entails supplementing the training data of the model with the adversarial examples generated from other white-box models in the same domain. As shown in [1], these examples, which are generated through optimizing the delta between the model's prediction function and the label, often transfer. Thus, it is possible to generate likely adversarial examples, and train on them, even without access to the specific model source.

### Model Architecture

In addition to additional training data, several  model-based approaches have successfully reduced the dimensionality of the adversarial cone, the subspace of adversarial examples.
_Defensive distillation_ [2], a variant on a technique traditionally used for computational gain, works by feeding class probability vectors for an image back through the deep neural network. The effect of this retraining is to smooth the decision boundaries of the model, thus improving its susceptibility to the adversarial samples that present with noisy gradients.

### Loss Function

Other efforts have reshaped the learning process with the addition of new loss terms. _Metric learning_ [3] adds to the objective function a triplet loss term, denoted (x<sub>a</sub>, x<sub>p</sub>, x<sub>n</sub>), where (x<sup>i</sup><sub>a</sub>, x<sup>i</sup><sub>p</sub>) are a positive pair (elements of the same class) and (x<sup>i</sup><sub>a</sub>, x<sup>i</sup><sub>n</sub>) are a negative pair (elements of different classes). By forcing examples of the same class together, the adversarial examples become closer to their true class in the embedded representation space.
Conceptually, the triplet loss idea is not dissimilar from _logit pairing_ [4], which introduces a logit loss term with pairs of clean images and their adversarial pairs. While the introduction of logit pairing improves upon traditional adversarial training, _logit squeezing_ [4] outperformed logit pairing on the benchmark dataset MNIST. Logit squeezing uses the same loss term $\lambda L(f'(x), f(x))$ as logit pairing, with an added penalty term on the norm of the logit. _Feature scattering_ [5] leverages inter-sample relationships as well, using bilevel optimization to maximize the distance between original and perturbed examples in adversarial training.

### Feature Space

Some adversarial defenses target not the models themselves, but the feature space. _Feature squeezing_ [6] is a method its creators describe as borne of the observation that "feature input spaces are often unnecessarily large, and this vast input space provides extensive opportunities for an adversary." The inputs to the model are projected onto a lower-dimension feature space, by either reducing pixel color depth or smoothing the image spatially, resulting in coalescence of similar examples into a single input.
_Feature denoising_ [7] takes a similar approach, applying a set of denoising operations with local and non-local filters. _Sequence squeezing_ [8] is an analogous input reduction mechanism for use with recurrent neural networks.

### Formal Certification

Finally, _certified defenses_ [9] guarantee an upper bound on the worst-case loss for several model types such as linear classifiers and neural networks, formulating the adversarial loss as a semidefinite program.

## Assessment

### Primary Defenses

The first adversarial defenses I would support in a product are ensemble adversarial training and feature squeezing and denoising. In my opinion, changes to model architecture and the loss function are more potent but also require more buy-in and a greater impact on existing systems.

Consider adversarial training first. This is low-hanging fruit, because the training and sample generation can be done entirely outside the existing pipeline, with the only tangible impact being a larger training dataset. Furthermore, because we transfer examples of an ensemble of other models within the computer vision space, the same generation could likely several many different customers. And although more sophisticated methods outperform ensemble adversarial training, oftentimes that alone can reap a large proportion of the maximum observed benefit.

Working in the feature space has similar advantages. Denoising images is an easily scaled functionality, and could be added to the existing preprocessing suite. Feature squeezing would be the same. This step could follow immediately from the adversarial sample generation in [1] as well as the standard procedures for data augmentation (cropping, rotation, etc.). Both of these steps also have the advantage of being highly intuitive in explanation.

### Secondary Defenses

The second group of defenses I would support are changes to the loss function, followed by changes to model architecture (namely distillation). As mentioned, the efficacy of these methods has in many cases been more impressive than either in the previous category. However, changes to the training methodology are in general more disruptive. Of the loss function additions, I believe metric learning is the most promising avenue, combining much of the information gleaned from both logit pairing and feature squeezing. Defensive distillation could be extremely beneficial to DNN learning, but requires re-architecture of the system, and is less interpretable than any of the previous methods.

### Exclusions

I would not focus on the formal certification of performance. Although a provable upper bound is appealing from a sales standpoint, especially with government customers, I believe the line of exploration is at this point more academic than practical. Derivations of neural networks with one and two layers are complete, but as the neural network architectures increase in complexity, the method does not scale well enough to support state-of-the-art DNN-based systems. Similarly, sequence squeezing is probably not applicable enough to the majority of computer vision systems to justify its implementation.

## Product Recommendation

The adversarial defense product would be most effective if integrated into the ML pipeline. As described in the previous section, the selected defenses should be integrated at certain points within the existing system, with dataset augmentation occurring first chronologically, followed by feature space reductions, then loss and architectural alterations.

Given that we have in essence a set of cheaper defenses which provide significant gain, and a set of higher-effort defenses which will likely another performance improvement, I could envision two tiered offerings which include only the first set and both sets respectively.

Although the tool should be integrated into the client pipeline, I think there's some flexibility with respect to the way in which it is integrated. My recommendation would be an API. For the procedures in the lower-tier offering, it would be sufficient for the client to pass in their datasets. For the higher-tier offering, the client would pass in additional objects including the objective function and the neural net.

## Sources

1. [Ensemble Adversarial Training: Attacks and Defenses](https://arxiv.org/pdf/1705.07204.pdf)
2. [Distillation as a Defense to Adversarial Perturbations](https://arxiv.org/pdf/1511.04508.pdf)
3. [Metric Learning for Adversarial Robustness](https://arxiv.org/abs/1909.00900)
4. [Adversarial Logit Pairing](https://arxiv.org/pdf/1803.06373.pdf)
5. [Defense Against Adversarial Attacks Using Feature Scattering-based Adversarial Training](https://arxiv.org/pdf/1801.09344.pdf)
6. [Feature Squeezing: Detecting Adversarial Examples in Deep Neural Networks](https://arxiv.org/pdf/1704.01155.pdf)
7. [Feature Denoising for Improving Adversarial Robustness](https://arxiv.org/pdf/1812.03411v2.pdf)
8. [Defense Methods Against Adversarial Examples for Recurrent Neural Networks](https://arxiv.org/pdf/1901.09963.pdf)
9. [Certified Defenses Against Adversarial Examples](https://arxiv.org/pdf/1801.09344.pdf)
