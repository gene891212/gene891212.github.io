---
layout: home
author_profile: true
---

## 我的專案列表

<div class="entries-grid">
  {% if site.github.public_repositories %}
    {% assign sorted_repos = site.github.public_repositories | sort: "stargazers_count" | reverse %}
    {% for repo in sorted_repos %}
      {% if repo.has_pages and repo.name != "gene891212.github.io" %}
        <div class="grid-item-container">
          <article class="archive__item" style="height: 100%; border: 1px solid #f2f3f3; padding: 1.5em; border-radius: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); display: flex; flex-direction: column;">
            <h2 class="archive__item-title no_toc" style="margin-top: 0; font-size: 1.25rem;">
              <a href="https://gene891212.github.io/{{ repo.name }}">{{ repo.name }}</a>
            </h2>
            <div class="archive__item-excerpt" style="flex-grow: 1;">
              <p>{{ repo.description | default: "尚未提供專案描述。" }}</p>
            </div>
            <div style="margin-top: 15px; font-size: 0.8em; color: #666; border-top: 1px solid #eee; padding-top: 10px;">
              <span style="margin-right: 15px;"><i class="fas fa-star"></i> {{ repo.stargazers_count }}</span>
              {% if repo.language %}
                <span><i class="fas fa-code"></i> {{ repo.language }}</span>
              {% endif %}
            </div>
          </article>
        </div>
      {% endif %}
    {% endfor %}
  {% else %}
    <p>正在從 GitHub 載入專案資料，請稍候...</p>
  {% endif %}
</div>

<style>
  .entries-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
    gap: 1.5rem;
    align-items: stretch; /* 確保每一行卡片高度一致 */
  }
  
  .grid-item-container {
    display: flex;
  }

  .archive__item {
    width: 100%;
  }

  .archive__subtitle, .pagination {
    display: none !important;
  }
</style>