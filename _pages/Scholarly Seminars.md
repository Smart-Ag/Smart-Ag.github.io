---
layout: page
title: Scholarly Seminars
permalink: /scholarly seminars
description: 实验室例会与学术报告
nav: true
nav_order: 4
display_categories: [Presentations, Conferences]
horizontal: false
---

<!-- 增强样式：确保导航栏“Scholarly Seminars”不换行，同时修复项目卡片布局 -->
<style>
  /* ----- 导航栏链接强制不换行（兼顾空格编码问题） ----- */
  nav a[href*="scholarly seminars"],
  nav a[href*="scholarly%20seminars"] {
    white-space: nowrap !important;
    display: inline-block !important;   /* 防止被父级 flex 压缩换行 */
    max-width: none !important;         /* 取消任何可能限制宽度的属性 */
  }

  /* 如果上述仍无效，可以尝试给父级 li 添加属性（兼容性良好） */
  nav li:has(a[href*="scholarly"]) {
    flex-shrink: 0;                     /* 禁止在 flex 容器中被压缩 */
    white-space: nowrap;
  }

  /* 针对旧浏览器（不支持 :has）的备选方案：通过 JavaScript 添加类，此处略 */

  /* ----- 以下是你原有的项目卡片布局修正（保持每行一个项目）----- */
  .projects .row-cols-1.row-cols-md-3 {
    display: block !important;
  }
  
  .projects .row-cols-1.row-cols-md-3 > * {
    width: 100% !important;
    max-width: 100% !important;
    flex: 0 0 100% !important;
  }
  
  .projects .row-cols-1.row-cols-md-2 {
    display: block !important;
  }
  
  .projects .row-cols-1.row-cols-md-2 > * {
    width: 100% !important;
    max-width: 100% !important;
    flex: 0 0 100% !important;
  }
  
  .projects .container {
    padding-left: 0 !important;
    padding-right: 0 !important;
  }
  
  .projects .row {
    margin-left: 0 !important;
    margin-right: 0 !important;
  }

  /* ----- 左侧锚点导航栏样式 ----- */
  .side-nav {
    position: fixed;
    left: 20px;
    top: 50%;
    transform: translateY(-50%);
    background: rgba(255, 255, 255, 0.95);
    border-radius: 12px;
    padding: 16px 0;
    box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
    z-index: 1000;
    min-width: 140px;
  }

  .side-nav ul {
    list-style: none;
    padding: 0;
    margin: 0;
  }

  .side-nav li {
    margin: 0;
  }

  .side-nav a {
    display: block;
    padding: 12px 20px;
    color: #333;
    text-decoration: none;
    font-size: 14px;
    transition: all 0.3s ease;
    border-left: 3px solid transparent;
  }

  .side-nav a:hover {
    background: #f5f5f5;
    border-left-color: #007bff;
    color: #007bff;
  }

  .side-nav a.active {
    background: #e8f4fd;
    border-left-color: #007bff;
    color: #007bff;
    font-weight: 600;
  }

  /* 响应式调整：小屏幕隐藏侧边导航 */
  @media (max-width: 768px) {
    .side-nav {
      display: none;
    }
  }
</style>

<!-- 左侧锚点导航栏 -->
<div class="side-nav">
  <ul>
    <li><a href="#Presentations">Presentations</a></li>
    <li><a href="#Conferences">Conferences</a></li>
  </ul>
</div>

<!-- 页面主要内容（沿用之前的 projects 布局） -->
<div class="projects">
{% if site.enable_project_categories and page.display_categories %}
  <!-- 分类展示项目 -->
  {% for category in page.display_categories %}
  <a id="{{ category }}" href=".#{{ category }}">
    <h2 class="category">{{ category }}</h2>
  </a>
  {% assign categorized_projects = site.projects | where: "category", category %}
  {% assign sorted_projects = categorized_projects | sort: "importance" | reverse %}
  <!-- 根据 horizontal 参数生成卡片 -->
  {% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
  {% endfor %}

{% else %}

<!-- 无分类时，直接展示所有项目 -->
{% assign sorted_projects = site.projects | sort: "importance" | reverse %}

  <!-- 根据 horizontal 参数生成卡片 -->
{% if page.horizontal %}
  <div class="container">
    <div class="row row-cols-1 row-cols-md-2">
    {% for project in sorted_projects %}
      {% include projects_horizontal.liquid %}
    {% endfor %}
    </div>
  </div>
  {% else %}
  <div class="row row-cols-1 row-cols-md-3">
    {% for project in sorted_projects %}
      {% include projects.liquid %}
    {% endfor %}
  </div>
  {% endif %}
{% endif %}
</div>