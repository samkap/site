---
title: Posts
permalink: "/posts/"
Key: 
layout: page
---

## Articles, thoughts, and long-form.

{% for post in site.posts %}
 {% unless post.next %}<h3>{{ post.date | date: '%Y' }}</h3>
{% else %}{% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}{% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
{% if year != nyear %}<h3>{{ post.date | date: '%Y' }}</h3>{% endif %}
{% endunless %}
 {% if post.categories contains "clips" or post.categories contains "food" %}
 {% else if %}
<article>
<p><a href="{{ post.url }}">{{ post.title }}</a> • <small>{{ post.date | date: site.date_format }}</small></p>
</article>
 {% endif %}  
 {% endfor %}