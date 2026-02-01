---
layout: page
permalink: /teaching/
title: teaching
description: 
nav: true
nav_order: 4
lake_pic: lake-pics/lake-teaching.jpg
---

I have extensive teaching experience with courses of different levels (BA/BSc; MA; PhD) aimed at diverse student populations (linguistics, philosophy, language education, general education classes). Currently I teach  at the University College Utrecht, a liberal arts & sciences college of Utrecht University, where I direct the study program in linguistics and offer courses on language, logic and argumentation:

* Introduction to rhetoric and informal logic: Argumentation, persuasion, manipulation
* Formal logic for open minds
* Introduction to linguistics: The science of language
* Syntax and semantics: Language form and meaning
* Pragmatics: Meaning and reasoning in conversation

Additionally, I strongly believe in cross-fertilization across disciplinary boundaries and am committed to teaching at language, logic and information summer schools held under the auspices of [FoLLI](https://folli.info/). See below for materials.

 <br>  <br>  <br> 


<!-- pages/teaching.md -->
<div class="teaching">
{% if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized teaching -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_teaching = site.teaching | where: "category", category %}
  {% assign sorted_teaching = categorized_teaching | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_teaching %}
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

<!-- Display teaching without categories -->

{% assign sorted_teaching = site.teaching | sort: "year" | reverse %}

  <!-- Generate cards for each project -->

{% if page.horizontal %}

  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_teaching %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_teaching %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>
