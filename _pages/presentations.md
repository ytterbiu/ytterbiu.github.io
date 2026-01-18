---
layout: page
title: Presentations
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
  {% assign sep = "" %}

{% if p.slides %} <a href="{{ p.slides | relative_url }}">Slides/PDF</a>
{% assign sep = " · " %} {% endif %}

{% if p.video %} {{ sep }}<a href="{{ p.video }}">Video</a>
{% assign sep = " · " %} {% endif %}

{% if p.website %} {{ sep }}<a href="{{ p.website }}">Event page</a>
{% assign sep = " · " %} {% endif %}

{% if p.abstract_url %}
{{ sep }}<a href="{% if p.abstract_url contains '://' %}{{ p.abstract_url }}{% else %}{{ p.abstract_url | relative_url }}{% endif %}">
{{ p.abstract_label | default: "Abstract" }} </a> {% endif %}

</div>
  </li>
{% endfor %}
</ul>
