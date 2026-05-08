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

These days, you can find my writing at [No Failsafe](https://nofailsafe.substack.com/), a Substack I co-write with Numa Dhamani covering AI safety, security, and trust. We cover how the threat landscape is evolving with today's advanced AI systems.

I contributed to the [Integrity Institute response]() to NIST's RFI on agentic security and authored a [report](https://gifct.org/wp-content/uploads/2023/09/GIFCT-23WG-0823-GenerativeAI-1.1.pdf) on generative AI and online extremism for the [Global Internet Forum to Counter Terrorism](https://gifct.org/). Earlier writing includes [pieces](https://techpolicy.press/solarwinds-hack-signals-necessity-of-federal-breach-notification-law/) for [Tech Policy Press](https://techpolicy.press/new-eu-privacy-rule-may-complicate-moderation-of-child-sexual-abuse-material/), [New_ Public](https://newpublic.org/article/1954/how-zero-trust-security-locks-out-marginalized-internet-users), and the Integrity Institute [blog](https://integrityinstitute.org/our-ideas/hear-from-our-fellows/middleware-and-the-customization).


I've also given talks at [SXSW](https://schedule.sxsw.com/events/PP1162552), [TrustCon](https://www.trustcon.net/), [#NSGSCon](https://nsgscon.com/), [Art into Science: A Conference for Defense](https://artintoscience.com/), and other tech and security conferences.

