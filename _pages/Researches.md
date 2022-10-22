---
layout: page
title: Researches
permalink: /Researches/
description: A growing collection of your cool projects.
nav: true
nav_order: 2
display_categories: [work, fun]
horizontal: false
---

<!-- pages/Researches.md -->
<div class="Researches">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized Researches. -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_Researches. = site.Researches | where: "category", category -%}
  {%- assign sorted_Researches. = categorized_Researches. | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_Researches. -%}
      {% include Researches._horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_Researches. -%}
      {% include Researches.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display Researches. without categories -->
  {%- assign sorted_Researches. = site.Researches | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_Researches. -%}
      {% include Researches._horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_Researches. -%}
      {% include Researches.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
