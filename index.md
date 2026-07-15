---
permalink: /
published: true
title: Уроки информатики
date: 2026-06-08
---
{% for project in site.projects %}
  <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
{% endfor %}
## Последние исследования

{% for post in site.posts limit:100 %}
  - <b>{{ post.date | date: "%Y-%m-%d" }}</b>: 
    [{{ post.title }}](/honey{{ post.url }})
{% endfor %}

{% if site.posts.size == 0 %}
  <p>Пока нет ни одного поста. Создай файл в папке _posts/ с названием YYYY-MM-DD-nazvanie.md</p>
{% endif %}
# Прочие проекты
{% for repository in site.github.public_repositories %}
  * [{{ repository.name }}]({{ repository.html_url }})
{% endfor %}