---
layout: page
permalink: /news/
title: News
description: News in reverse chronological order.
nav: true
nav_order: 1
---

{% assign news_items = site.news | sort: "date" | reverse %}

<div class="news-list">
  {% for item in news_items %}
    <article class="news-entry mb-5">
      <header>
        <h2 class="h4 mb-1">
          <time datetime="{{ item.date | date_to_xmlschema }}">
            {{ item.date | date: "%b %-d, %Y" }}
          </time>
          — {{ item.title }}
        </h2>
      </header>
      <div class="news-content">
        {{ item.content }}
      </div>
    </article>
  {% endfor %}
</div>
