---
layout: page
title: Home
permalink: /en/
lang: en
alt_url: /
nav: false
---

<div class="en-home" style="font-family: 'Times New Roman', serif;">

<p style="font-size: 20px; text-indent: 2em; line-height: 1.8;">
  Our mission is to apply advanced ideas of robotics, artificial intelligence, machine vision, remote sensing,
  data mining and information technology to smart agriculture. The core techniques include 2D / 3D image processing,
  multispectral / hyperspectral imaging, spectroscopy, deep learning, machine learning, digital mapping and
  biochemical sensing. The tools available for our research include unmanned aerial vehicles, unmanned ground vehicles,
  RGB and multispectral cameras, hyperspectral cameras, DGPS, and various electrical, optical and chemical sensors.
</p>

<h2 style="margin-top: 2rem;">Research Areas</h2>

<ul style="font-size: 18px; line-height: 1.9;">
  <li>Agricultural robots for kiwifruit and apple orchards (harvesting, pollination, thinning, pruning)</li>
  <li>Machine vision, 3D perception and deep learning for plant and fruit phenotyping</li>
  <li>Remote sensing and UAV-based field phenotyping and yield estimation</li>
  <li>Smart orchard production: sensing, decision-making and intelligent equipment</li>
</ul>

<h2 style="margin-top: 2rem;">Latest News</h2>

{% assign news_items = site.data.en.announcements %}
{% if news_items and news_items.size > 0 %}
<div class="table-responsive">
  <table class="table table-sm table-borderless">
    {% for item in news_items limit: 10 %}
      <tr>
        <th scope="row" style="width: auto; vertical-align: top; white-space: nowrap;">
          {% if item.date %}{{ item.date | date: '%b %d, %Y' }}{% endif %}
        </th>
        <td>
          {% if item.link and item.link != '' %}
            <a href="{{ item.link }}" target="_blank" rel="noopener">{{ item.title }}</a>
          {% else %}
            {{ item.title }}
          {% endif %}
        </td>
      </tr>
    {% endfor %}
  </table>
</div>
<p style="margin-top: 1rem;">
  <a href="{{ '/en/news/' | relative_url }}">All news &rarr;</a>
</p>
{% else %}
<p>No news yet.</p>
{% endif %}

<h2 style="margin-top: 2rem;">Explore</h2>

<ul style="font-size: 18px; line-height: 1.9;">
  <li><a href="{{ '/en/publications/' | relative_url }}">Publications</a></li>
  <li><a href="{{ '/en/news/' | relative_url }}">Lab News</a></li>
  <li><a href="{{ '/en/contact/' | relative_url }}">Contact Us</a></li>
</ul>

</div>
