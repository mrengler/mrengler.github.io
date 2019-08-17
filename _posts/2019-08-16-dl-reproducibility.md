---
title: 'Benchmarks, Deep Learning Research, and Rewards'
id: 1
excerpt: A recap of some questions on reproducibility in deep learning.
date: 2019-08-13
permalink: /posts/2019/08/deep-learning-reproducibility/
tags:
  - deep learning
  - machine learning
---

## The Reproducibility Crisis Coming to Deep Learning

This week at work my team discussed a recent paper, with the great title [Are We Really Making Much Progress? A Worrying Analysis of Recent Neural Recommendation Approaches](https://arxiv.org/abs/1907.06902). As the abstract states, "With the strongly increased interest in machine learning in general, it has, as a result, become difficult to keep track of what represents the state-of-the-art at the moment, e.g., for top-n recommendation tasks. At the same time, several recent publications point out problems in today's research practice in applied machine learning, e.g., in terms of the reproducibility of the results or the choice of the baselines when proposing new models." The authors ended up replicating tthe algorithms introduced in eighteen papers that were presented at conferences in the past couple years, and were able to reproduce results for only seven. Several did not report information on hyperparameter tuning, and at least one reported their results at different epochs, choosing the best one for each metric.

There are a lot of issues to pick apart here, including outright bad science. I'd like to start by reiterating that each paper reviewed here was published at a top-tier conference: these papers are exactly what these venues reward. At a meta-level, it's not clear that this paper itself would be accepted any of those places, although we are increasingly starting to recognize the importance of this methodology work. By and large, the research that is most prominent and well-funded aims for "state-of-the-art" performance on a benchmark dataset, espcially attained through the use of a novel algorithm. Benchmark datasets are wonderful for allowing comparable model evaluations. But what are we really achieving with dozens of slightly tweaked algorithms, each gaining 0.01% in test accuracy on ImageNet or CIFAR-10? I am not alone in thinking that it doesn't seem like the best use of resources.

My colleage, Bronwyn Woods, presented a short thinkpiece at last year's Critiquing and Correcting Trends in Machine Learning workshop at NeurIPS. I recommend reading [the whole thing](https://arxiv.org/abs/1812.01495), but one of her main arguments was that—if a machine learning task is a combination of data, an algorithm, and a target—the only real exploration is done in the algorithm space, to our detriment. Firstly, with the novel work presented it's often not clear _where_ the gain is coming from (whether it is caused by the technical innovation, or clever tuning). Secondly, I think it's likely we'll continue to see this sort of p-hacking that was present in the reviewed example until, like Bronwyn writes, contributions to these other stages are also incentivized. I'm reminded of a study (I've forgotten who did this) maybe a couple years ago where a classifier was trained, successfully, on ten of the most commonly used image datasets. The model was able to determine to a high degree of accuracy which set any image came from, no matter the subject. It's such a fascinating result because we're collectively patting ourselves on the backs for solving computer vision, when clearly there are some artifacts in the photos, but these toy datasets are our only metric of comparison.

Still, I'm optimistic. With workshops like CRACT and an increasing push towards publishing code and data with papers, we'll begin to have the infrastructure in place to correct mistakes like these, and to invite the creativity required to move from beyond the closed world and into the real one.
