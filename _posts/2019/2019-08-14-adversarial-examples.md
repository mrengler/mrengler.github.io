---
title: 'Constraints on Adversarial Examples'
id: 1
excerpt: My thoughts on why implicit constraints could hold the key to usable adversarial examples.
date: 2019-08-13
permalink: /posts/2019/08/adversarial-examples-constraints/
tags:
  - adversarial learning
  - machine learning
---

## Adversarial Learning's Constraint Problem

Adversarial learning has generated a lot of eye-catching headlines recently, in many cases for good reason. For the uninitiated, the way this works is basically this: instead of training a single model to, for example, detect stop signs in images, you train two models simultaneously. The first one trains as usual—given a large dataset of labeled images, model weights are learned by optimizing for accuracy on the dataset, so that the model can predict "stop sign" or "not stop sign" for a given new image. The second model is a generative network that creates new images, usually through perturbations of training examples, and trains *on the outputs of the first model*. Its objective is to create images that the first model misclassifies, and it is optimized to do just that. Those images, wherein the first model thinks there's no stop sign but there is, or thinks there's a stop sign when there isn't, are adversarial examples.

This is an intentional oversimplification, but usefully illustrates the dangers associated with insufficiently robust machine learning systems. If a self-driving car's computer vision system could no longer identify a stop sign based on the placement of a few stickers, as shown by researchers in [Robust Physical-World Attacks on Deep Learning Visual Classification](https://arxiv.org/pdf/1707.08945.pdf), that's a problem. And these examples don't always require a lot of time and compute power. Some are even [naturally occuring](https://arxiv.org/abs/1907.07174). 

There is a broader discussion to be had here about what we still [don't understand about deep learning](https://arxiv.org/abs/1907.06902), but I'd like to focus on one particular critique of adversarial learning work. In several domains, adversarial examples are shrugged off as interesting, but irrelevant, because the perturbations render the input unusable for its original purpose.

In cybersecurity, ML-powered solutions analyze binaries of known malicious and benign executables in order to detect malware. An adversarial example in this area could be disastrous, leading to the exploitation of a protected network, loss of sensitive data, and other catastrophic outcomes. But it's really hard to perform adversarial learning while ensuring that the malicious binary remains functional. To return to the image example, we can imagine the various tiny alterations that the second model could learn, updating pixel values to blur edges or reduce contrast. Unless these changes are extreme, a picture of a stop sign is still going to look like a picture of a stop sign, and would be perceived as such by a human. On the other hand, flipping a single bit of a malware binary could render it ineffective.

This isn't to say that there aren't known ways to alter files while maintaining the same behavior. Since the time of signature-based antivirus platforms, malware authors have used file packing, obfuscation, and randomly generated strings to ensure that the binaries they release look new to such systems. But it's hard to automate these changes in such a way that the same behavior is guaranteed. The potency of adversarial examples is limited by constraint expression. There's no way to specify a constraint that says the binary should still execute, or that an example should be indistinguishable from the original input in other, specific ways. The approximation of many of these constraints are open questions. For example, although I don't know of such a heuristic, we could likely express "indistinguishable to the human eye" as a function of distance between images. Instead of purely generating adversarial examples, the community should focus on learning constraints like these [implicitly](https://arxiv.org/pdf/1805.10561.pdf). Only then will we be able to meaningfully understand the boundaries of the problem spaces we are in, and measure the shortcomings of existing models appropriately. 
