---
layout: page
title: Scholarly Seminars
permalink: /en/seminars/
lang: en
alt_url: /scholarly seminars
nav: true
nav_order: 4
---

{% assign all_items = site.data.en.seminars %}
{% assign conf = all_items | where: "category", "Conferences" | sort: "date" | reverse %}
{% assign pres = all_items | where: "category", "Presentations" | sort: "date" | reverse %}

<style>
  .en-seminars { max-width: 1050px; margin: 0 auto; font-family: 'Times New Roman', serif; }
  .en-seminars h2 { font-size: 1.45rem; color: #2c3e50; margin: 2rem 0 1rem; padding-bottom: .4rem; border-bottom: 2px solid #3498db; }
  .en-seminars .grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(290px, 1fr)); gap: 1.2rem; }
  .en-seminars .card-item { border: 1px solid #eaeaea; border-radius: 8px; overflow: hidden; background: #fff; }
  .en-seminars .card-item img { width: 100%; height: 170px; object-fit: cover; display: block; }
  .en-seminars .card-item .body { padding: .7rem .85rem; }
  .en-seminars .card-item .t { font-size: 1rem; color: #2c3e50; font-weight: 600; line-height: 1.35; }
  .en-seminars .card-item .m { font-size: .88rem; color: #7f8c8d; margin-top: .3rem; }
</style>

<div class="en-seminars">

  <h2 id="Conferences">Conferences &amp; Invited Talks</h2>
  <div class="grid">
    {% for item in conf %}
    <div class="card-item">
      {% if item.img %}<img src="{{ item.img | relative_url }}" alt="{{ item.title }}" loading="lazy">{% endif %}
      <div class="body">
        <div class="t">{{ item.title }}</div>
        <div class="m">{{ item.speaker }}</div>
        <div class="m">{{ item.date | date: "%B %d, %Y" }}</div>
      </div>
    </div>
    {% endfor %}
  </div>

  <h2 id="Presentations">Lab Group Meetings</h2>
  <div class="grid">
    {% for item in pres %}
    <div class="card-item">
      {% if item.img %}<img src="{{ item.img | relative_url }}" alt="{{ item.title }}" loading="lazy">{% endif %}
      <div class="body">
        <div class="t">{{ item.title }}</div>
        <div class="m">{{ item.speaker }}</div>
        <div class="m">{{ item.date | date: "%B %d, %Y" }}</div>
      </div>
    </div>
    {% endfor %}
  </div>

</div>
