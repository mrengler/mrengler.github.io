---
layout: archive
title: "Selected Works"
permalink: /works/
author_profile: true
output: 
  html_document:
    includes:
       in_header: GA_Script.html
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %}

These days, you can find my writing at [No Failsafe](https://nofailsafe.substack.com/), a Substack I co-write with Numa Dhamani covering AI safety, security, and trust.

In 2023, I had the distinct honor and privilege of being part of the [GIFCT Red Teaming Working Group](https://gifct.org/year-three-working-groups/#), and coordinating its work on generative AI. In that capacity, I authored a [report](https://gifct.org/wp-content/uploads/2023/09/GIFCT-23WG-0823-GenerativeAI-1.1.pdf) on the impacts of generative AI on online terrorism and extremism, and spoke at a UN General Assembly Side Event cohosted by GIFCT and the UN Security Council Counter-Terrorism Committee Executive Directorate – the discussion was recorded [here](https://gifct.org/2023/09/20/unga2023/).

I have written blog posts for the [Integrity Institute](https://integrityinstitute.org/our-ideas/hear-from-our-fellows/middleware-and-the-customization) and [Harvard Business School](https://digital.hbs.edu/platforms-crowds/how-brands-unwittingly-fund-disinformation/) reported and published a story for the [New Public_](https://newpublic.org/) online magazine on the [accessibility of Zero Trust](https://newpublic.org/article/1954/how-zero-trust-security-locks-out-marginalized-internet-users), and have contributed various opinion pieces and explainers to [Tech Policy Press](https://techpolicy.press/) on topics like the [detection toolset for child sexual abuse material](https://techpolicy.press/new-eu-privacy-rule-may-complicate-moderation-of-child-sexual-abuse-material/) as it relates to data privacy and [the need for a federal breach notification law](https://techpolicy.press/solarwinds-hack-signals-necessity-of-federal-breach-notification-law/).   

I've also given talks at [TrustCon](https://www.trustcon.net/), [#NSGSCon](https://nsgscon.com/), [Art into Science: A Conference for Defense](https://artintoscience.com/), and other security-related conferences.