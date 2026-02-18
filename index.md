---
layout: home
author_profile: true
---

---
layout: home
author_profile: true
---

## 我的專案列表

<div class="grid__wrapper custom-repo-grid">
  {% for repo in site.github.public_repositories %}
    {% if repo.has_pages and repo.name != "gene891212.github.io" %}
      <div class="grid__item">
        <article class="archive__item repo-card">
          <h2 class="archive__item-title">
            <a href="https://gene891212.github.io/{{ repo.name }}">{{ repo.name }}</a>
          </h2>
          {% if repo.description %}
            <p class="archive__item-excerpt">{{ repo.description }}</p>
          {% else %}
            <p class="archive__item-excerpt" style="color: #999; font-style: italic;">尚無專案描述</p>
          {% endif %}
          <div class="repo-meta">
            <span><i class="fas fa-star"></i> {{ repo.stargazers_count }}</span>
            <span class="separator">|</span>
            <span><i class="fas fa-code"></i> {{ repo.language }}</span>
          </div>
        </article>
      </div>
    {% endif %}
  {% endfor %}
</div>

<style>
  /* 隱藏多餘元件 */
  .archive__subtitle, .pagination {
    display: none !important;
  }

  /* 讓卡片高度整齊一致 */
  .custom-repo-grid {
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
  }

  .repo-card {
    border: 1px solid #e1e4e8 !important;
    padding: 24px !important;
    border-radius: 12px !important;
    background: #fff;
    transition: all 0.3s ease;
    height: 100%; /* 確保內容撐開 */
    display: flex;
    flex-direction: column;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
  }

  /* 滑鼠移動上去的效果 */
  .repo-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 8px 15px rgba(0,0,0,0.1);
    border-color: #0366d6 !important;
  }

  .archive__item-title {
    margin-top: 0 !important;
    font-size: 1.25rem !important;
  }

  .archive__item-excerpt {
    flex-grow: 1; /* 讓描述佔滿空間，推擠下方標籤對齊 */
    font-size: 0.9rem;
    color: #586069;
    margin-bottom: 15px;
  }

  .repo-meta {
    font-size: 0.85rem;
    color: #6a737d;
  }

  .separator {
    margin: 0 8px;
    color: #d1d5da;
  }
</style>