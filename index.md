---
layout: home
author_profile: true
---

## 我的專案列表 (自動更新)

<div class="grid__wrapper">
  {% for repo in site.github.public_repositories %}
    {% if repo.has_pages and repo.name != "gene891212.github.io" %}
      <div class="grid__item">
        <article class="archive__item" style="border: 1px solid #eee; padding: 20px; border-radius: 10px;">
          <h2 class="archive__item-title">
            <a href="https://gene891212.github.io/{{ repo.name }}">{{ repo.name }}</a>
          </h2>
          <p class="archive__item-excerpt">{{ repo.description }}</p>
          <p><i class="fas fa-star"></i> {{ repo.stargazers_count }} | <i class="fas fa-code"></i> {{ repo.language }}</p>
        </article>
      </div>
    {% endif %}
  {% endfor %}
</div>
