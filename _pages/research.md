---
layout: page
title: research
permalink: /research/
description: 🎯 I am deeply passionate about leveraging automated solutions to tackle challenges in Software Engineering. My research focuses on Automated Program Repair (APR), Program Analysis, Software Repository Mining, and AI for Software Engineering (AI4SE). I explore cutting-edge techniques to enhance software quality, reliability, and maintainability through automation and intelligent systems. 🚀
nav: true
nav_order: 3
display_categories: ["Code Reliability", "Code Quality"]
horizontal: false
---

<!-- pages/research.md -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized research -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_research = site.research | where: "category", category %}
  {% assign sorted_research = categorized_research | sort: "importance" %}
  <!-- Generate cards for each research item -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for research in sorted_research %}
      {% include research_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for research in sorted_research %}
      {% include research.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- Display research without categories -->

{% assign sorted_research = site.research | sort: "importance" %}

  <!-- Generate cards for each research item -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for research in sorted_research %}
      {% include research_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for research in sorted_research %}
      {% include research.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>

