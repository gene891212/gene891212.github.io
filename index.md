---
layout: home
author_profile: true
---

## 我的專案列表

<div class="entries-grid">
  {% assign sorted_repos = site.github.public_repositories | sort: "stargazers_count" | reverse %}
  {% for repo in sorted_repos %}
    {% if repo.has_pages and repo.name != "gene891212.github.io" %}
      <div class="list__item">
        <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork" style="height: 100%; border: 1px solid #f2f3f3; padding: 1.5em; border-radius: 8px; box-shadow: 0 1px 3px rgba(0,0,0,0.05); display: flex; flex-direction: column;">
          <h2 class="archive__item-title no_toc" itemprop="headline" style="margin-top: 0;">
            <a href="https://gene891212.github.io/{{ repo.name }}" rel="permalink">{{ repo.name }}</a>
          </h2>
          <div class="archive__item-excerpt" itemprop="description" style="flex-grow: 1;">
            <p>{{ repo.description | default: "尚未提供專案描述。" }}</p>
          </div>
          <div style="margin-top: 15px; font-size: 0.8em; color: #666;">
            <span style="margin-right: 15px;"><i class="fas fa-star" aria-hidden="true"></i> {{ repo.stargazers_count }}</span>
            {% if repo.language %}
              <span><i class="fas fa-code" aria-hidden="true"></i> {{ repo.language }}</span>
            {% endif %}
          </div>
        </article>
      </div>
    {% endif %}
  {% endfor %}
</div>

<style>
  /* 修正網格排列，確保一行四個或隨螢幕縮放 */
  .entries-grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(250px, 1fr));
    gap: 1.5em;
    margin-top: 1em;
  }
  /* 移除底部 Recent Posts 標題 (如果該區塊沒內容) */
  .archive__subtitle {
    display: none;
  }
</style>