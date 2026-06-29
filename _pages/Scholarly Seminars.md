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

  /* ----- 左侧锚点导航栏样式（现代化设计）----- */
  .side-nav {
    position: fixed;
    left: 30px;
    top: 50%;
    transform: translateY(-50%);
    background: linear-gradient(145deg, #ffffff, #f8f9fa);
    border-radius: 16px;
    padding: 8px;
    box-shadow:
      0 8px 32px rgba(0, 0, 0, 0.08),
      0 2px 8px rgba(0, 0, 0, 0.04),
      inset 0 1px 0 rgba(255, 255, 255, 0.8);
    z-index: 1000;
    min-width: 160px;
    border: 1px solid rgba(0, 0, 0, 0.05);
  }

  /* 导航栏标题 */
  .side-nav .nav-title {
    text-align: center;
    font-size: 11px;
    font-weight: 600;
    color: #999;
    text-transform: uppercase;
    letter-spacing: 1px;
    padding: 12px 16px 8px;
    margin: 0;
    border-bottom: 1px solid rgba(0, 0, 0, 0.05);
  }

  .side-nav ul {
    list-style: none;
    padding: 4px 0;
    margin: 0;
  }

  .side-nav li {
    margin: 2px 4px;
    border-radius: 8px;
    overflow: hidden;
  }

  .side-nav a {
    display: flex;
    align-items: center;
    padding: 10px 16px;
    color: #555;
    text-decoration: none;
    font-size: 14px;
    font-weight: 500;
    transition: all 0.25s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
  }

  /* 图标装饰 */
  .side-nav a::before {
    content: '';
    width: 6px;
    height: 6px;
    background: #ddd;
    border-radius: 50%;
    margin-right: 10px;
    transition: all 0.25s ease;
  }

  .side-nav li:hover {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    box-shadow: 0 4px 16px rgba(102, 126, 234, 0.3);
    transform: translateX(2px);
  }

  .side-nav li:hover a {
    color: #fff;
    padding-left: 20px;
  }

  .side-nav li:hover a::before {
    background: #fff;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
  }

  /* 当前激活项 */
  .side-nav li.active {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
    box-shadow: 0 4px 16px rgba(102, 126, 234, 0.3);
  }

  .side-nav li.active a {
    color: #fff;
    padding-left: 20px;
  }

  .side-nav li.active a::before {
    background: #fff;
    box-shadow: 0 0 8px rgba(255, 255, 255, 0.5);
  }

  /* 底部装饰 */
  .side-nav::after {
    content: '';
    position: absolute;
    bottom: -4px;
    left: 20%;
    right: 20%;
    height: 8px;
    background: rgba(102, 126, 234, 0.1);
    border-radius: 50%;
    filter: blur(8px);
  }

  /* 响应式调整：小屏幕隐藏侧边导航 */
  @media (max-width: 992px) {
    .side-nav {
      display: none;
    }
  }
</style>

<!-- 左侧锚点导航栏 -->
<div class="side-nav">
  <h4 class="nav-title">Quick Nav</h4>
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
