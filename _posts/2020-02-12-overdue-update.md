---
title: 'GDI's Approach in Countering Disinformation'
id: 5
excerpt: It's not easy to change the adtech ecosystem, but we're going to try.
date: 2020-02-12
permalink: /posts/2020/02/update/
tags:
  - disinformation
  - personal
---

Last month, I gave a talk on the state of authentication at [Art into Science 2020](https://artintoscience.com/), a low-key security conference focused on defense and hosted right here in Austin. It was my last remaining responsibility pertaining to my role at Duo, which I exited at the end of December. I have moved into a role as the lead data scientist for [Global Disinformation Index](https://disinformationindex.org/),  a nonprofit I had already been consulting with for the last six months or so. I'd like to take some time to talk about GDI's mission in particular (I'm hoping to start writing more, and more often, about our work).

First, there is a natural overlap between information security and information operations, influence operations, or information warfare. Scholars like Sam Woolley at the University of Texas, political scientists and other groups have long studied the influence of propaganda and false news on elections; in the United States, this inevitable entwinement between security and disinformation became clear after the interference of the Russian government in the 2016 presidential election, but similar practices occurred in other countries (especially Ukraine, well-known to the cyber community as Russia's sandbox). However, I think another way in which the two fields are similar is that there is almost too much focus and emphasis on the most sophisticated, nation-state operations. The reality is that these actors make up a small percentage of both hacking and disinforming activity.

Duo's co-founders, Dug Song and Jon Oberheide, decided to found a security company together before they even knew what they wanted to build. But they wanted to found it on the principle of democratizing security: making a solution that was accessible to customers large and small. The problem that Dug and Jono ended up solving was multi-factor authentication. MFA isn't sexy, but its effectiveness is almost unparalleled. When we consider the proportion of breaches that occur because of stolen credentials, and the level of _difficulty_ introduced by MFA towards credential theft, it has to be among the greatest security successes ever. It's not perfect—authentication factors can be spoofed, and individual targets are still vulnerable to a variety of other hacks—but the economics of the attack completely change. If someone is targeting a company that has deployed multi-factor, they suddenly have to work a lot harder than bulk credential-stuffing from password dictionaries and getting access to a dozen accounts immediately. And if that work is hard enough, with a rate of success low enough, the financial incentives disappear.

At Global Disinformation Index, we do not aim to be arbiters of truth. We know that we will not be able to detect any false statements on the Internet. What we want to do is make it harder for people to get rich by making false statements on the Internet: to remove the financial incentives. Again, this won't deter state actors, sponsored by their governments, but it could very well impact someone looking to make a quick buck. Plenty of other institutions, like Atlantic Council's DFR Lab, Stanford Internet Observatory, think tanks, and for-profit companies all report on government-backed disinformation campaigns. We view our focus on monetization as both our differentiator and a means to have direct and measurable impact. When we identify adversarial narratives, such as propaganda, hate speech, and misinformation, we flag the websites hosting that content to ad exchanges. Then, the exchanges providing revenue to those domains by serving ads can make an informed determination about whether that content is something they want to support. Our goal is to cut off the money flowing into disinformation, shrink the marketplace, and discourage perpetrators.

We've got a lot to do.

