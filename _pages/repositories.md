---
layout: page
title: repositories
permalink: /repositories/
description: representative code repositories.
nav: true
nav_order: 3
---

<style>
  .repo-list {
    display: grid;
    gap: 1rem;
    margin-top: 1rem;
  }

  .repo-item {
    border-bottom: 1px solid var(--global-divider-color);
    padding: 0 0 1rem;
  }

  .repo-item:last-child {
    border-bottom: 0;
  }

  .repo-title {
    align-items: baseline;
    display: flex;
    flex-wrap: wrap;
    gap: 0.5rem 0.75rem;
    margin-bottom: 0.25rem;
  }

  .repo-title a {
    color: var(--global-theme-color);
    font-size: 1.05rem;
    font-weight: 700;
  }

  .repo-meta {
    color: var(--global-text-color-light);
    font-size: 0.875rem;
  }

  .repo-description {
    margin: 0.35rem 0 0.45rem;
  }

  .repo-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.35rem;
    margin: 0;
    padding: 0;
  }

  .repo-tags li {
    border: 1px solid var(--global-divider-color);
    border-radius: 0.25rem;
    color: var(--global-text-color-light);
    display: inline-block;
    font-size: 0.78rem;
    list-style: none;
    padding: 0.1rem 0.45rem;
  }
</style>

<div class="repo-list">
  {% for repo in site.data.repositories.featured_repos %}
    <article class="repo-item">
      <div class="repo-title">
        <a href="{{ repo.url }}" rel="external nofollow noopener" target="_blank">{{ repo.name }}</a>
        <span class="repo-meta">{{ repo.repo }}{% if repo.language %} · {{ repo.language }}{% endif %}</span>
      </div>
      <p class="repo-description">{{ repo.description }}</p>
      {% if repo.tags %}
        <ul class="repo-tags" aria-label="{{ repo.name }} tags">
          {% for tag in repo.tags %}
            <li>{{ tag }}</li>
          {% endfor %}
        </ul>
      {% endif %}
    </article>
  {% endfor %}
</div>
