---
layout: page
title: presentations
permalink: /presentations/
description: Talks, posters, invited lectures, and workshops.
nav: true
nav_order: 5
---

{% assign items = site.presentations | sort: "date" | reverse %}

<ul class="list-unstyled">
{% for p in items %}
  <li class="mb-3">
    <div><strong>{{ p.title }}</strong></div>
    <div class="text-muted">
      {{ p.type | capitalize }} · {{ p.venue }} · {{ p.location }} · {{ p.date | date: "%b %Y" }}
    </div>
    <div>
      {% if p.slides %}<a href="{{ p.slides | relative_url }}">Slides/PDF</a>{% endif %}
      {% if p.video %}{% if p.slides %} · {% endif %}<a href="{{ p.video }}">Video</a>{% endif %}
      {% if p.website %}{% if p.slides or p.video %} · {% endif %}<a href="{{ p.website }}">Event page</a>{% endif %}
      {% if p.url %}{% if p.slides or p.video or p.website %} · {% endif %}<a href="{{ p.url | relative_url }}">Details</a>{% endif %}
    </div>
  </li>
{% endfor %}
</ul>
