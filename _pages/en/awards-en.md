---
layout: page
title: Awards
permalink: /en/awards/
lang: en
alt_url: /awards/
nav: true
nav_order: 6
---

{% assign awards = site.data.en.awards %}
{% assign years = awards | map: "year" | uniq | sort | reverse %}
{% assign student_n = awards | where: "type", "student" | size %}
{% assign faculty_n = awards | where: "type", "faculty" | size %}

<style>
  .en-awards { max-width: 1000px; margin: 0 auto; font-family: 'Times New Roman', serif; }
  .en-awards h2 { font-size: 1.45rem; color: #2c3e50; margin: 2rem 0 1rem; padding-bottom: .4rem; border-bottom: 2px solid #3498db; }
  .en-awards .stats { display: flex; gap: 2.5rem; justify-content: center; background: #f8f9fa; border: 1px solid #eaeaea; border-radius: 8px; padding: 1rem; }
  .en-awards .stats .num { font-size: 1.7rem; font-weight: 700; color: #2c3e50; text-align: center; }
  .en-awards .stats .lbl { font-size: .9rem; color: #7f8c8d; text-align: center; }
  .en-award { border-left: 3px solid #3498db; padding: .55rem .9rem; margin-bottom: .8rem; background: #fbfcfd; }
  .en-award .prize { display: inline-block; background: #3498db; color: #fff; font-size: .78rem; padding: .12rem .5rem; border-radius: 10px; margin-right: .5rem; vertical-align: middle; }
  .en-award .prize.faculty { background: #8e44ad; }
  .en-award .title { font-size: 1.02rem; color: #2c3e50; }
  .en-award .meta { font-size: .88rem; color: #7f8c8d; margin-top: .15rem; }
</style>

<div class="en-awards">

  <div class="stats">
    <div><div class="num">{{ awards | size }}</div><div class="lbl">Total awards</div></div>
    <div><div class="num">{{ student_n }}</div><div class="lbl">Student awards</div></div>
    <div><div class="num">{{ faculty_n }}</div><div class="lbl">Faculty honours</div></div>
  </div>

  {% for y in years %}
    <h2>{{ y }}</h2>
    {% assign items = awards | where: "year", y %}
    {% for a in items %}
      <div class="en-award">
        {% if a.prize %}<span class="prize{% if a.type == 'faculty' %} faculty{% endif %}">{{ a.prize }}</span>{% endif %}
        <span class="title">{{ a.title }}</span>
        <div class="meta">
          {% if a.month %}{{ a.month }}/{{ y }}{% endif %}
          {% if a.participant %} · {{ a.participant }}{% endif %}
          {% if a.competition %} · {{ a.competition }}{% endif %}
        </div>
        {% if a.note %}<div class="meta"><em>{{ a.note }}</em></div>{% endif %}
      </div>
    {% endfor %}
  {% endfor %}

</div>
