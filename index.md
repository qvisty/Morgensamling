---
layout: default
title: Oversigt
---

# Morgensamling

Korte, kreative morgensamlinger til efterskoleelever.

<ul class="samling-liste">
{% assign sorted = site.samlinger | sort: "dato" | reverse %}
{% for samling in sorted %}
  <li>
    <a href="{{ samling.url | relative_url }}">{{ samling.title }}</a>
    <div class="meta">{{ samling.dato }} &middot; {{ samling.tema }}</div>
  </li>
{% endfor %}
</ul>
