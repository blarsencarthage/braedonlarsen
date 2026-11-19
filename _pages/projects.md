---
layout: page
title: portfolio
permalink: /portfolio/
description: placeholder
nav: true
nav_order: 1
dropdown: true
children:
  # The Portfolio menu. When you add a project in _projects/, add a line here with its title and permalink.
  - title: overview
    permalink: /portfolio/
  - title: divider
  - title: M.U.T.T. (2025)
    permalink: /portfolio/mutt/
  - title: EP4 Internship (2026)
    permalink: /portfolio/ep4-internship/
  - title: Microgravity Lab
    permalink: /portfolio/microgravity-lab/
  - title: Engineering Thesis
    permalink: /portfolio/engineering-thesis/
  - title: Engineering Practice
    permalink: /portfolio/engineering-practice/
  - title: Collegiate Rocket Launch
    permalink: /portfolio/rocket-launch/
  - title: Project Hail Mary
    permalink: /portfolio/project-hail-mary/
  - title: In-Class Lectures
    permalink: /portfolio/in-class-lectures/
  - title: Elevator Pitch
    permalink: /portfolio/elevator-pitch/
---

<!-- Each entry is generated from a file in _projects/ (ordered by "importance"): title, role, description and img come from that file's front matter. -->

{% assign sorted_projects = site.projects | sort: "importance" %}
{% for project in sorted_projects %}
{% assign side = forloop.index | modulo: 2 %}

<div style="display: flex; flex-wrap: wrap; gap: 1.5rem; align-items: center; margin: 2rem 0;{% if side == 0 %} flex-direction: row-reverse;{% endif %}">
  <div style="flex: 3 1 320px;">
    <h3 style="margin-bottom: 0.25rem;"><a href="{{ project.url | relative_url }}">{{ project.title }}</a></h3>
    <p style="margin-bottom: 0.5rem;"><strong>{{ project.role }}</strong></p>
    <p>{{ project.description }}</p>
    <p><a href="{{ project.url | relative_url }}">Read more &rarr;</a></p>
  </div>
  {% if project.img %}
  <div style="flex: 2 1 240px;">
    <a href="{{ project.url | relative_url }}"><img src="{{ project.img | relative_url }}" alt="{{ project.title }}" class="img-fluid rounded z-depth-1" style="width: 100%;"></a>
  </div>
  {% endif %}
</div>
{% unless forloop.last %}<hr>{% endunless %}
{% endfor %}
