---
layout: page
permalink: /tech
title: tech
nav: true
pagination:
  permalink: /tech/:num/
  enabled: true
  per_page: 1
  sort_field: date
  sort_reverse: true
  trail:
    before: 1 # The number of links before the current page
    after: 3  # The number of links after the current page
---

<div class="posts">
  <ul class="post-list">
    {% for tech in site.categories.tech %}
      <li>
        <h3>
          <a class="post-title" href="{{ tech.url | prepend: site.baseurl }}">
          {{ tech.title }}
          </a>
        </h3>
        {% if tech.tags %}
          {% for tag in tech.tags %} <span class="card-tag">{{ tag }}</span>
          {% endfor %}
        {% endif %}
        <p class="post-meta">{{ tech.date | date: '%B %-d, %Y' }}</p>
        <p>{{ tech.description }}</p>
      </li>
    {% endfor %}
  </ul>

  {% include pagination.html %}

</div>
