---
layout: default
title: "Radixhomework"
---

<div class="hero">
  <div class="radix-mark" aria-hidden="true">
    <span>R</span>
  </div>

  <p class="eyebrow">Personal projects, made from home</p>

  <h1>RadixHomeWork</h1>

  <p class="hero-intro">
    A small personal workshop for worlds, games, tools, illustrations
    and whatever else happens to take root.
  </p>
</div>

<div class="ornament" aria-hidden="true">
  <span class="ornament-symbol">✦</span>
</div>

<section>
  <h2>Projects</h2>

  <div class="project-grid">
    {% assign projects = site.projects | sort: "order" %}
    {% for project in projects %}
      <article class="project-card">
        {% if project.status %}
          <p class="project-type">{{ project.status }}</p>
        {% endif %}

        <h3>
          <a href="{{ project.url | relative_url }}">{{ project.title }}</a>
        </h3>

        {% if project.short_description %}
          <p>{{ project.short_description }}</p>
        {% endif %}

        <a class="project-link" href="{{ project.url | relative_url }}">
          Discover the project →
        </a>
      </article>
    {% endfor %}
  </div>
</section>
