---
layout: home
author_profile: true
title: "我的專案列表"
---

### Github Page

<div class="grid__wrapper custom-repo-grid">
  {% for repo in site.github.public_repositories %}
    {% if repo.has_pages and repo.name != "gene891212.github.io" %}
      <div class="grid__item">
        <article class="archive__item repo-card">
          <h2 class="archive__item-title">
            <a href="https://gene891212.github.io/{{ repo.name }}">{{ repo.name }}</a>
          </h2>
          <div class="excerpt-container">
            {% if repo.description %}
              <p class="archive__item-excerpt">{{ repo.description }}</p>
            {% else %}
              <p class="archive__item-excerpt no-desc">尚無專案描述</p>
            {% endif %}
          </div>
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
  /* 隱藏主題生成的重複副標題 */
  .archive__subtitle, .pagination {
    display: none !important;
  }

  /* 讓列表更緊湊以容納 3 個 */
  .custom-repo-grid {
    display: grid !important;
    /* 這裡把 240px 改成 180px，確保能塞下 3 個 */
    grid-template-columns: repeat(auto-fill, minmax(180px, 1fr)) !important;
    gap: 10px !important; /* 縮小間隙 */
    margin-top: 15px !important;
    clear: both !important;
  }

  .custom-repo-grid .grid__item {
    float: none !important;
    width: auto !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  .repo-card {
    border: 1px solid #e1e4e8 !important;
    padding: 12px !important; /* 再縮小一點內距 */
    border-radius: 8px !important;
    background: #fff;
    height: 100%;
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    transition: all 0.2s;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
  }

  .repo-card:hover {
    transform: translateY(-2px);
    border-color: #0366d6 !important;
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
  }

  .archive__item-title {
    margin: 0 0 5px 0 !important;
    font-size: 1rem !important; /* 稍微縮小字體以適應窄卡片 */
    font-weight: bold;
  }

  /* 統一描述文字高度，最多顯示 3 行 */
  .excerpt-container {
    flex-grow: 1;
    display: -webkit-box;
    -webkit-line-clamp: 3; 
    -webkit-box-orient: vertical;
    overflow: hidden;
    margin-bottom: 10px;
  }

  .archive__item-excerpt {
    font-size: 0.8rem !important;
    color: #586069;
    margin: 0 !important;
    line-height: 1.4;
  }

  .no-desc {
    color: #cfd8dc !important;
    font-style: italic;
  }

  .repo-meta {
    font-size: 0.75rem;
    color: #6a737d;
    padding-top: 8px;
    border-top: 1px solid #f6f8fa;
  }

  .separator {
    margin: 0 4px;
    color: #d1d5da;
  }
</style>