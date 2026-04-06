---
page_id: news
layout: page
title: News
permalink: /news/
title: News
description: 
nav: true
nav_order: 4
---

---

<!-- {% include news.liquid %} -->

{% assign items = site.news | sort: 'date' | reverse %}
{% assign groups = items | group_by_exp: 'item', 'item.date | date: "%Y"' %}

{% for year in groups %}

### {{ year.name }}

<ul>
  {% for item in year.items %}
    <li>
      <span style="color:#888">{{ item.date | date: "%Y-%m-%d" }}</span>
      — <a href="{{ item.url | relative_url }}">{{ item.title }}</a>
    </li>
  {% endfor %}
</ul>
{% endfor %}
