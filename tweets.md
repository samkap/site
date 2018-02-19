---
title: Tweets
permalink: "/tweets/"
position: 1
layout: page
---

## Test page for backing up tweets


{% assign tweets = site.tweets | reverse %}
{% for post in tweets  %}
{% unless post.next %}<h3>{{ post.date | date: '%Y' }}</h3>
{% else %}{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}<h3>{{ post.date | date: '%Y' }}</h3>{% endif %}
{% endunless %}
<p><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a><small> • {{ post.date | date: site.date_format }}</small></p>
  {% endfor %}