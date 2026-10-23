---
layout: page
title: News
permalink: /en/news/
lang: en
alt_url: /news/
nav: false
---

<div class="news-archive" style="font-family: 'Times New Roman', serif;">

{% assign sorted_news = site.data.en.announcements %}

{% for item in sorted_news %}
  <div class="news-item mb-5">
    <div class="news-header mb-3">
      {% if item.date %}
        <span class="news-date badge bg-secondary">
          <i class="fas fa-calendar-alt me-1"></i>
          {{ item.date | date: "%B %d, %Y" }}
        </span>
      {% endif %}
      {% if item.category %}
        <span class="news-category badge bg-primary ms-2">{{ item.category }}</span>
      {% endif %}
    </div>

    <h2 class="news-title" style="font-size: 1.15rem; border-bottom: 1px solid #eee; padding-bottom: 10px;">
      {% if item.link and item.link != "" %}
        <a href="{{ item.link }}" target="_blank" rel="noopener" class="text-decoration-none">
          {{ item.title }}
          <i class="fas fa-external-link-alt fa-xs ms-1"></i>
        </a>
      {% else %}
        {{ item.title }}
      {% endif %}
    </h2>

    {% if item.description %}
      <p class="news-description lead">{{ item.description }}</p>
    {% endif %}
  </div>

  {% unless forloop.last %}<hr class="my-5">{% endunless %}
{% endfor %}

{% if sorted_news.size == 0 %}
  <div class="text-center py-5">
    <i class="fas fa-newspaper fa-3x text-muted mb-3"></i>
    <h3>No news yet</h3>
    <p class="text-muted">Check back later for updates.</p>
  </div>
{% endif %}

</div>
