---
layout: page
title: Tags
permalink: /tags/
---

{% assign tags = site.tags | sort %}

<div class="tag-cloud">
  {% for tag in tags %}
    <a href="#{{ tag[0] | slugize }}" style="margin-right: 15px;">
      {{ tag[0] }} ({{ tag[1].size }})
    </a>
  {% endfor %}
</div>

<hr>

{% for tag in tags %}
  <h2 id="{{ tag[0] | slugize }}">{{ tag[0] }}</h2>
  <ul>
    {% for post in tag[1] %}
      <li>
        <a href="{{ post.url }}">{{ post.title }}</a>
        <small>({{ post.date | date: "%B %d, %Y" }})</small>
      </li>
    {% endfor %}
  </ul>
{% endfor %}
