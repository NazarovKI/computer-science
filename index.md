---
permalink: /
published: true
title: Уроки информатики
date: 2026-06-08
---
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
## Последние исследования

{% for post in site.posts limit:100 %}
  - <b>{{ post.date | date: "%Y-%m-%d" }}</b>: 
    [{{ post.title }}](/computer-science{{ post.url }})
{% endfor %}

{% if site.posts.size == 0 %}
  <p>Пока нет ни одного поста. Создай файл в папке _posts/ с названием YYYY-MM-DD-nazvanie.md</p>
{% endif %}
# Прочие проекты
{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}