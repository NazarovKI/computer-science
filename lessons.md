---
layout: default
title: "Все уроки информатики"
permalink: /lessons/
---

<h1>{{ page.title }}</h1>

<ul>
  {% for lesson in site.lessons %}
    <li>
      <a href="{{ lesson.url | relative_url }}">
        <h2>{{ lesson.title }}</h2>
      </a>
      {% if lesson.excerpt %}
        <p>{{ lesson.excerpt }}</p>
      {% endif %}
      <p><small>Дата: {{ lesson.date | date: "%d.%m.%Y" }}</small></p>
      <p>
        {% for tag in lesson.tags %}
          <span class="tag">#{{ tag }}</span>
        {% endfor %}
      </p>
    </li>
  {% endfor %}
</ul>