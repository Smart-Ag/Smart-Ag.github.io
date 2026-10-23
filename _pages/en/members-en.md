---
layout: page
title: Members
permalink: /en/members/
lang: en
alt_url: /members/
nav: true
nav_order: 7
---

{% assign faculty = site.data.en.members.faculty %}
{% assign current = site.data.en.members.current %}
{% assign graduated = site.data.en.members.graduated %}
{% assign cur_n = current | size %}
{% assign grad_n = graduated | size %}
{% assign total_n = cur_n | plus: grad_n %}
{% assign phd_current = current | where: "degree", "PhD student" %}
{% assign ms_current = current | where: "degree", "Master's student" %}
{% assign phd_grad = graduated | where: "degree", "PhD" %}
{% assign ms_grad = graduated | where: "degree", "Master's" %}

<style>
  .en-team { max-width: 1100px; margin: 0 auto; font-family: 'Times New Roman', serif; }
  .en-team h2 { font-size: 1.6rem; color: #2c3e50; margin: 2.5rem 0 1.2rem; padding-bottom: .5rem; border-bottom: 2px solid #3498db; }
  .en-team h3 { font-size: 1.15rem; color: #555; margin: 1.8rem 0 .9rem; }
  .en-stats { display: flex; justify-content: space-around; background: #f8f9fa; border: 1px solid #eaeaea; border-radius: 8px; padding: 1.2rem; margin-top: 1.5rem; }
  .en-stats div { text-align: center; }
  .en-stats .num { font-size: 1.9rem; font-weight: 700; color: #2c3e50; }
  .en-stats .lbl { font-size: .95rem; color: #7f8c8d; }
  .en-card { display: flex; gap: 1rem; border: 1px solid #eaeaea; border-radius: 8px; padding: .8rem; background: #fff; margin-bottom: 1rem; align-items: center; }
  .en-card img { width: 92px; height: 118px; object-fit: cover; border-radius: 6px; flex-shrink: 0; }
  .en-card .ph { width: 92px; height: 118px; border-radius: 6px; background: #f0f0f0; display: flex; align-items: center; justify-content: center; color: #aaa; font-size: .75rem; flex-shrink: 0; }
  .en-card .name { font-size: 1.1rem; font-weight: 700; color: #2c3e50; }
  .en-card .role { color: #3498db; font-weight: 600; font-size: .95rem; }
  .en-card .meta { color: #7f8c8d; font-size: .9rem; }
  .en-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(320px, 1fr)); gap: 1rem; }
  @media (max-width: 576px) { .en-grid { grid-template-columns: 1fr; } }
</style>

<div class="en-team">

  <div class="en-stats">
    <div><div class="num">{{ cur_n }}</div><div class="lbl">Current students</div></div>
    <div><div class="num">{{ grad_n }}</div><div class="lbl">Alumni</div></div>
    <div><div class="num">{{ total_n }}</div><div class="lbl">Total</div></div>
  </div>

  <h2>Faculty</h2>

  {% for person in faculty %}
  <div class="en-card">
    {% if person.photo %}<img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">{% else %}<div class="ph">Photo</div>{% endif %}
    <div>
      <div class="name">{{ person.name }}</div>
      <div class="role">{{ person.title }}</div>
      {% if person.degree %}<div class="meta">{{ person.degree }}</div>{% endif %}
      {% if person.research_interest %}<div class="meta"><strong>Research:</strong> {{ person.research_interest }}</div>{% endif %}
      {% if person.email %}<div class="meta"><strong>Email:</strong> {{ person.email }}</div>{% endif %}
    </div>
  </div>
  {% endfor %}

  <h2>Current Students</h2>

  <h3>PhD students ({{ phd_current | size }})</h3>
  <div class="en-grid">
    {% for person in phd_current %}
    <div class="en-card">
      {% if person.photo %}<img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">{% else %}<div class="ph">Photo</div>{% endif %}
      <div>
        <div class="meta">Enrolled {{ person.year }}</div>
        <div class="name">{{ person.name }}</div>
        <div class="meta">{{ person.degree }}</div>
      </div>
    </div>
    {% endfor %}
  </div>

  <h3>Master's students ({{ ms_current | size }})</h3>
  <div class="en-grid">
    {% for person in ms_current %}
    <div class="en-card">
      {% if person.photo %}<img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">{% else %}<div class="ph">Photo</div>{% endif %}
      <div>
        <div class="meta">Enrolled {{ person.year }}</div>
        <div class="name">{{ person.name }}</div>
        <div class="meta">{{ person.degree }}</div>
      </div>
    </div>
    {% endfor %}
  </div>

  <h2>Alumni</h2>

  <h3>PhD graduates ({{ phd_grad | size }})</h3>
  <div class="en-grid">
    {% for person in phd_grad %}
    <div class="en-card">
      {% if person.photo %}<img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">{% else %}<div class="ph">Photo</div>{% endif %}
      <div>
        <div class="meta">{{ person.year }}</div>
        <div class="name">{{ person.name }}</div>
        {% if person.graduation_destination %}<div class="meta"><strong>Now:</strong> {{ person.graduation_destination }}</div>{% endif %}
      </div>
    </div>
    {% endfor %}
  </div>

  <h3>Master's graduates ({{ ms_grad | size }})</h3>
  <div class="en-grid">
    {% for person in ms_grad %}
    <div class="en-card">
      {% if person.photo %}<img src="{{ person.photo | relative_url }}" alt="{{ person.name }}" loading="lazy">{% else %}<div class="ph">Photo</div>{% endif %}
      <div>
        <div class="meta">{{ person.year }}</div>
        <div class="name">{{ person.name }}</div>
        {% if person.graduation_destination %}<div class="meta"><strong>Now:</strong> {{ person.graduation_destination }}</div>{% endif %}
      </div>
    </div>
    {% endfor %}
  </div>

</div>
