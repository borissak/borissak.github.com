---
layout: archive
permalink: /
title: "보리싹의 기록노트"
excerpt: "안드로이드 개발 자료를 모으고 정리를 하는 기록노트입니다. "
image:
  feature: 
id: home
---

중요한것은 포기하지 않는 것이다.
더딘 것을 염려하지 말고, 멈출 것을 염려하라. --- *'아프니까 청춘이다'*
{:.shorten}

---

### [Articles <sup>{{ site.categories.articles.size }}</sup>]({{ site.url }}/articles/)

<div class="tiles">
{% for post in site.categories.articles limit:8 %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->
