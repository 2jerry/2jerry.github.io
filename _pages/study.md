---
layout: page
permalink: /study
title: study
nav: true
pagination:
  enabled: true
---
<div class="projects grid">
  
  {% assign sorted_projects = site.categories.study | sort: "importance" %}
  {% for project in sorted_projects %}
  
  <div class="grid-item">
    {% if project.redirect %}
    <a href="{{ project.redirect }}" target="_blank">
    {% else %}
    <a href="{{ project.url | relative_url }}">
    {% endif %}
      <div class="card hoverable">
        {% if project.img %}
        <img src="{{ project.img | relative_url }}" alt="project thumbnail">
        {% endif %}
        <div class="card-body">
          <h2 class="card-title text-lowercase">{{ project.title }}</h2>
          <p class="card-date">{{ project.date | date: '%B %-d, %Y' }}</p>
          <p class="card-text">{{ project.description }}</p>
          {% if project.tags %}
               {% for tag in project.tags %}
                <span class="card-tag">{{ tag }}</span>
               {% endfor %}
          {% endif %}
        </div>
      </div>
    </a>
  </div>
{% endfor %}
  {% include pagination.html %}

</div>
