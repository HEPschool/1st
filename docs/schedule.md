---
layout: default
permalink: /schedule/
title: Schedule
hero:
  image: "/assets/img/Feynman-diagram.webp"  # Optional
  title: "Schedule"
  subtitle: "Half-year plan"
---
# Schedule

You can view the details of each session by clicking on it.

<table>
<thead>
  <tr><th>Date/Time</th><th>Title</th><th>Speaker</th><th>Location</th><th>Note</th></tr>
</thead>
<tbody>
{% assign now_ts = site.time | date: '%s' | plus: 0 %}
{% assign cutoff_ts = now_ts | plus: 15811200 %}
{% assign all = site.events | sort: 'date' %}
{% assign shown = 0 %}
{% for ev in all %}
  {% assign ev_ts = ev.date | date: '%s' | plus: 0 %}
  {% if ev_ts >= now_ts and ev_ts <= cutoff_ts %}
  <tr onclick="location.href='{{ ev.url | relative_url }}'" style="cursor:pointer">
    <td>{{ ev.date | date: "%Y-%m-%d %H:%M" }}</td>
    <td>{{ ev.title }}</td>
    <td>{{ ev.speaker | default: "TBD" }}</td>
    <td>{{ ev.location }}</td><td>{{ ev.note | default: '' }}</td>
  </tr>
  {% assign shown = shown | plus: 1 %}
  {% endif %}
{% endfor %}
{% if shown == 0 %}
  {% for ev in all %}
  <tr onclick="location.href='{{ ev.url | relative_url }}'" style="cursor:pointer">
    <td>{{ ev.date | date: "%Y-%m-%d %H:%M" }}</td>
    <td>{{ ev.title }}</td>
    <td>{{ ev.speaker | default: "TBD" }}</td>
    <td>{{ ev.location }}</td><td>{{ ev.note | default: '' }}</td>
  </tr>
  {% endfor %}
{% endif %}
</tbody>
</table>
