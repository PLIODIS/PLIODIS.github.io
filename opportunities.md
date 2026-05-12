---
title: "Opportunities"
layout: splash
classes: wide
permalink: /opportunities/
header:
  overlay_image: /assets/images/Victoria.jpg
  overlay_filter: 0.3
---

## Open Positions

<div class="news-grid">
{% for opp in site.opportunities %}
  <a href="{{ opp.url | relative_url }}" class="news-card">
    {% if opp.header.overlay_image %}
      <div class="news-card-image" style="background-image: url('{{ opp.header.overlay_image }}')"></div>
    {% endif %}
    <div class="news-card-body">
      <p class="news-date">{{ opp.date | date: "%B %Y" }}</p>
      <h3>{{ opp.title }}</h3>
      <p>{{ opp.excerpt }}</p>
    </div>
  </a>
{% endfor %}
</div>