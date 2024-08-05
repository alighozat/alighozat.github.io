---
layout: page
title: Research
permalink: /projects/
description: 
nav: true
nav_order: 3
display_categories: [work, fun]
horizontal: false
---
<h2 style="text-align: center;">Water resources management and engineering</h2>
{% include figure.liquid loading="eager" path="assets/img/000.jpg" class="img-fluid rounded z-depth-1" %}
Water resources management and engineering encompass a wide range of critical activities aimed at ensuring sustainable and efficient use of water resources. Satellite datasets play a pivotal role in analyzing and evaluating environmental conditions, providing essential data for drought monitoring and forecasting, as well as flood inundation mapping and forecasting. Effective groundwater resources management relies on advanced techniques to monitor and regulate water levels, ensuring long-term sustainability. Forecasting water quality parameters is crucial for maintaining safe water supplies and protecting ecosystems from contamination. Multi-Criteria Decision-Making (MCDM) integrates various factors to assess risks, hazards, and vulnerabilities, enabling informed decisions in managing both surface and groundwater resources, especially during extreme events like floods and droughts.

<!-- pages/projects.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display projects without categories -->

{% assign sorted_projects = site.projects | sort: "importance" %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
