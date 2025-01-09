---
layout: page
permalink: /projects/
title: Teaching
description: A growing collection of educational materials
nav: true
nav_order: 3
display_categories: [Teaching Resources, Student Resources]
horizontal: false
---


### USC

TA / Pedagogy

* CSCI 401: Capstone: Design and Construction of Large Software Systems (Fall 2024)
* Future Faculty Teaching Institute Certification from Center for Excellence in Teaching (Fall 2023)
* CS@SC: Scratch (Fall 2022)

### UC Berkeley 

TA
* CS131: Computational Models of Cognition (Spring 2022)

Junior TA / Tutor
* Data100: Principles and Techniques of Data Science (Fall 2021)
* CS370:  Adaptive Instruction Methods in Computer Science (Spring 2021)
* CS61C: Machine Structures (Fall 2020)
* CS61B: Data Structures (Spring 2020)
* CS61A: Structure and Interpretation of Computer Programs (Fall 2019)
* Data8: Foundations of Data Science (Spring 2019)



This page is currently Under Construction :) 


<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
      {% include projects_horizontal.html %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
      {% include projects.html %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>

