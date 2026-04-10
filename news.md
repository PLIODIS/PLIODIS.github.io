---
title: "News"
layout: splash
classes: wide
permalink: /news/
header:
  overlay_image: /assets/images/Zambezi1.jpg
  overlay_filter: 0.3
---
## News
<div class="news-grid">
{% for post in site.posts %}
  <a href="{{ post.url | relative_url }}" class="news-card">
    {% if post.header.overlay_image %}
      <div class="news-card-image" style="background-image: url('{{ post.header.overlay_image }}')"></div>
    {% endif %}
    <div class="news-card-body">
      <p class="news-date">{{ post.date | date: "%B %Y" }}</p>
      <h3>{{ post.title }}</h3>
      <p>{{ post.excerpt }}</p>
    </div>
  </a>
{% endfor %}
</div>

![ZambeziRiver]({{ site.baseurl }}/assets/images/Zambezi1.jpg)
