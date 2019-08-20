---
layout: archive
title: "Projects"
permalink: /projects/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

## Duo

Although much of my work is internal-facing, I wrote about the future of passwordless authentication and performed all data analysis for Duo's [2019 Trusted Access Report](https://duo.com/resources/ebooks/the-2019-duo-trusted-access-report). Over 500,000 authentications per month are protected by Duo, so there was a lot to work with!
As part of my research, I also co-authored a blog post on [the state of healthcare security](https://duo.com/blog/the-state-of-trusted-access-in-healthcare).

## Cyence

One of the more fun whitepapers I've written was at Cyence, a startup in the cyber insurance space. I researched and drafted a [realistic threat scenario](https://www.aon.com/reinsurance/gimo/20181025-gimo-cyber) for an attack on a dam through its industrial control systems (ICS).

## Miscellaneous

[ScrAPD](scrapd.org) is "a small utility designed to help organizations retrieving traffic fatality data in a friendly manner." I contributed to the package as part of some work with [Open Austin](https://www.open-austin.org/), and co-maintain the parser, which scrapes the Austin Police Department's website and social media accounts.

Research I did as an undergraduate was published in PLOS ONE: [Somatic mutations render human exome and pathogen DNA more similar](https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0197949).

I gained my first exposure to NLP doing [multiple narrative disentanglement](http://cs229.stanford.edu/proj2016/poster/EnglerHarvey-MultipleNarrativeDisentanglement-Poster.pdf) for Andrew Ng's Machine Learning class.

I also completed a certificate program in science communication. Some of my technical writing, as well as meta-analysis of the program and the technical communication process, can be found [here](https://stanford.digication.com/maggie_engler/home-1).
