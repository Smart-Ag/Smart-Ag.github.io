---
layout: page
title: Resume
permalink: /en/cv/
lang: en
alt_url: /cv/
nav: true
nav_order: 1
---

{% assign cv = site.data.en.resume %}

<style>
  .en-cv { max-width: 950px; margin: 0 auto; font-family: 'Times New Roman', serif; line-height: 1.6; }
  .en-cv h2 { font-size: 1.35rem; color: #2c3e50; margin: 2rem 0 1rem; padding-bottom: .35rem; border-bottom: 2px solid #3498db; }
  .en-cv .top { display: flex; gap: 1.5rem; align-items: flex-start; }
  .en-cv .top img { width: 120px; height: 150px; object-fit: cover; border-radius: 8px; }
  .en-cv .name { font-size: 1.6rem; font-weight: 700; color: #2c3e50; }
  .en-cv .label { color: #3498db; font-weight: 600; }
  .en-cv .meta { color: #7f8c8d; font-size: .95rem; }
  .en-cv .row { display: flex; gap: 1rem; padding: .45rem 0; border-bottom: 1px dashed #eee; }
  .en-cv .when { min-width: 150px; color: #7f8c8d; font-size: .92rem; }
  .en-cv .what strong { color: #2c3e50; }
  .en-cv ul { margin: .3rem 0 .6rem 0; padding-left: 1.1rem; }
  .en-cv .note { color: #666; font-size: .92rem; }
</style>

<div class="en-cv">

  <div class="top">
    {% if cv.basics.image %}<img src="{{ cv.basics.image | relative_url }}" alt="{{ cv.basics.name }}">{% endif %}
    <div>
      <div class="name">{{ cv.basics.name }}</div>
      <div class="label">{{ cv.basics.label }}</div>
      <div class="meta">{{ cv.basics.email }} · {{ cv.basics.phone }}</div>
      <div class="meta">{{ cv.basics.location }}</div>
      <p class="note" style="margin-top:.5rem;">{{ cv.basics.summary }}</p>
    </div>
  </div>

  <h2>Education</h2>
  {% for e in cv.education %}
  <div class="row">
    <div class="when">{{ e.startDate }} – {{ e.endDate }}</div>
    <div class="what"><strong>{{ e.studyType }}</strong>, {{ e.field }}<br><span class="note">{{ e.institution }}, {{ e.location }}</span></div>
  </div>
  {% endfor %}

  <h2>Professional Experience</h2>
  {% for w in cv.work %}
  <div class="row">
    <div class="when">{{ w.startDate }} – {{ w.endDate }}</div>
    <div class="what"><strong>{{ w.position }}</strong><br><span class="note">{{ w.name }}{% if w.location %} · {{ w.location }}{% endif %}</span></div>
  </div>
  {% endfor %}

  <h2>Honours and Awards</h2>
  <ul>
    {% for a in cv.awards %}
    <li><strong>{{ a.title }}</strong> — {{ a.awarder }}{% if a.note %}<br><span class="note">{{ a.note }}</span>{% endif %}</li>
    {% endfor %}
  </ul>

  <h2>Editorial and Professional Service</h2>
  <ul>
    {% for s in cv.service %}
    <li><strong>{{ s.position }}</strong>, {{ s.organization }}{% if s.note %} <span class="note">— {{ s.note }}</span>{% endif %}</li>
    {% endfor %}
  </ul>

  <h2>Other Service</h2>
  <ul>
    {% for p in cv.projects %}
    <li><strong>{{ p.name }}</strong><br><span class="note">{{ p.summary }}</span></li>
    {% endfor %}
  </ul>

</div>
