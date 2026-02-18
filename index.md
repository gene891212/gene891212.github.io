---
layout: home
author_profile: true
title: "我的專案列表"
---

## Github Page

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
            <p class="archive__item-excerpt no-desc">尚無專案描述</p>
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
  /* 隱藏主題多餘元素 */
  .archive__subtitle, .pagination {
    display: none !important;
  }

  /* 緊湊型 Grid 佈局 */
  .custom-repo-grid {
    display: grid !important;
    grid-template-columns: repeat(auto-fill, minmax(220px, 1fr)) !important; /* 稍微縮小最小寬度 */
    gap: 12px !important; /* 緊湊間距 */
    margin: 10px 0 !important;
    clear: both !important;
  }

  /* 移除預設浮動與寬度限制 */
  .custom-repo-grid .grid__item {
    float: none !important;
    width: auto !important;
    margin: 0 !important;
    padding: 0 !important;
  }

  /* 緊湊型卡片設計 */
  .repo-card {
    border: 1px solid #e1e4e8 !important;
    padding: 16px !important; /* 縮小內距 */
    border-radius: 8px !important; /* 稍微減小圓角 */
    background: #fff;
    transition: all 0.2s ease-in-out;
    height: 100%;
    display: flex;
    flex-direction: column;
    box-sizing: border-box;
    box-shadow: 0 1px 3px rgba(0,0,0,0.05);
  }

  .repo-card:hover {
    transform: translateY(-3px);
    box-shadow: 0 4px 10px rgba(0,0,0,0.1);
    border-color: #0366d6 !important;
  }

  .archive__item-title {
    margin: 0 0 6px 0 !important; /* 極小化標題下邊距 */
    font-size: 1.1rem !important; /* 稍微調小字體 */
    line-height: 1.3 !important;
  }

  .archive__item-excerpt {
    flex-grow: 1;
    font-size: 0.85rem;
    color: #586069;
    margin: 0 0 12px 0 !important; /* 縮小描述下邊距 */
    line-height: 1.4;
  }

  .no-desc {
    color: #bdc3c7 !important;
    font-style: italic;
  }

  /* 底部資訊欄 */
  .repo-meta {
    font-size: 0.8rem;
    color: #6a737d;
    padding-top: 10px;
    border-top: 1px solid #f6f8fa;
  }

  .separator {
    margin: 0 6px;
    color: #d1d5da;
  }
</style>