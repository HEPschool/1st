---
layout: default
permalink: /materials/
title: Lecture Materials
hero:
  image: "/assets/img/Feynman-diagram.webp"  # Optional
  title: "Lecture Materials"
  subtitle: "Slides & notes"
---
# Lecture Materials

If you require access to the encrypted materials, please contact the author.

<ul>
  {% assign mats = site.data.materials | sort: "date" %}
  {% for m in mats %}
    {% assign href = m.file %}
    <li>
      <strong>{{ m.date }} · {{ m.title }}</strong> - {{ m.speaker }}
      {% if href contains '://' %}
        [ <a href="{{href}}" target="_blank" rel="noopener">PDF</a> ]
      {% else %}
        [ <a href="{{href | relative_url}}" target="_blank" rel="noopener">PDF</a> ]
      {% endif %}
    </li>
  {% endfor %}
</ul>
