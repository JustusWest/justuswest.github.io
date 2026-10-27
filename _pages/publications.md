---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if site.author.googlescholar %}
  You can also find my articles on <u><a href="{{ site.author.googlescholar }}">my Google Scholar profile</a>.</u>
{% endif %}

{% include base_path %}

{% assign pubs = site.publications | sort: "date" | reverse %}

## Conference Papers

{% for post in pubs %}{% if post.pubtype == "conference" %}
  {% include archive-single.html %}
{% endif %}{% endfor %}

## Journal Articles

{% for post in pubs %}{% if post.pubtype == "journal" %}
  {% include archive-single.html %}
{% endif %}{% endfor %}
