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

## General

In 2023, I had the distinct honor and privilege of being part of the [GIFCT Red Teaming Working Group](https://gifct.org/year-three-working-groups/#), and coordinating its work on generative AI. In that capacity, I authored a [report](https://gifct.org/wp-content/uploads/2023/09/GIFCT-23WG-0823-GenerativeAI-1.1.pdf) on the impacts of generative AI on online terrorism and extremism, and spoke at a UN General Assembly Side Event cohosted by GIFCT and the UN Security Council Counter-Terrorism Committee Executive Directorate – the discussion was recorded [here](https://gifct.org/2023/09/20/unga2023/).

I have written blog posts for the [Integrity Institute](https://integrityinstitute.org/our-ideas/hear-from-our-fellows/middleware-and-the-customization) and [Harvard Business School](https://digital.hbs.edu/platforms-crowds/how-brands-unwittingly-fund-disinformation/) reported and published a story for the [New Public_](https://newpublic.org/) online magazine on the [accessibility of Zero Trust](https://newpublic.org/article/1954/how-zero-trust-security-locks-out-marginalized-internet-users), and have contributed various opinion pieces and explainers to [Tech Policy Press](https://techpolicy.press/) on topics like the [detection toolset for child sexual abuse material](https://techpolicy.press/new-eu-privacy-rule-may-complicate-moderation-of-child-sexual-abuse-material/) as it relates to data privacy and [the need for a federal breach notification law](https://techpolicy.press/solarwinds-hack-signals-necessity-of-federal-breach-notification-law/).   

I've also given talks at [TrustCon](https://www.trustcon.net/), [#NSGSCon](https://nsgscon.com/), [Art into Science: A Conference for Defense](https://artintoscience.com/), and other security-related conferences.


## Global Disinformation Index

As part of my work at GDI, I am responsible for our ad revenue estimation capabilities from end-to-end. A recent report on COVID-19 disinformation was featured in [Forbes](https://www.forbes.com/sites/isabeltogoh/2020/07/08/google-and-amazon-are-inadvertently-funding-covid-conspiracy-sites-to-the-tune-of-25-million/#521107467d96), [Fast Company](https://www.fastcompany.com/90514329/google-is-placing-ads-next-to-health-misinformation-on-conspiracy-sites), [Bloomberg](https://www.bloomberg.com/news/articles/2020-06-01/google-helps-place-ads-on-sites-amplifying-covid-19-conspiracies), and other outlets.

Our report on the monetization of disinformation in violation of the European Union Code of Conduct, was covered as an exclusive by the [Financial Times](https://www.ft.com/content/5f8a405c-c132-4d9b-a86f-c52884535f3e), and later referenced by [Politico](https://www.politico.eu/newsletter/brussels-playbook/politico-brussels-playbook-stay-home-but-poles-apart-vaccine-info-wars/) and [VICE Magazine](https://www.vice.com/en_us/article/z3bkz9/google-is-putting-amazon-prime-ads-on-russia-backed-sites-spreading-coronavirus-conspiracies). You can find the full report [on our website](https://disinformationindex.org/wp-content/uploads/2020/03/GDI_Adtech_EU.pdf).


## Duo
I wrote the survey questions, performed data analysis, and wrote Duo's 2019 [State of the Auth](https://duo.com/blog/the-2019-state-of-the-auth-report-has-2fa-hit-mainstream-yet), a census-representative survey designed to measure adoption and usage of multi-factor authentication. The report was covered in [Dark Reading](https://www.darkreading.com/application-security/younger-generations-drive-bulk-of-2fa-adoption/d/d-id/1336581).
I also owned all data analysis and supported content creation for Duo's [2019 Trusted Access Report](https://duo.com/resources/ebooks/the-2019-duo-trusted-access-report). That report was picked up by [ZDNet](https://www.zdnet.com/pictures/2019s-tech-security-and-authentication-trends/), [CSO](https://www.csoonline.com/article/3409785/companies-with-zero-trust-network-security-move-toward-biometric-authentication.html), [Dark Reading](https://www.darkreading.com/cloud/security-snapshot-os-authentication-browser-and-cloud-trends/d/d-id/1335262), [Security Week](https://www.securityweek.com/enterprises-showing-increasing-backing-zero-trust-authentication), and [Infosecurity Magazine](https://www.infosecurity-magazine.com/news/businesses-shine-a-light-on-shadow/), among many others (hats off to the PR team). We focused on pillars of the zero-trust security framework.
