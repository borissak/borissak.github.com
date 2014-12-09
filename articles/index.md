---
layout: archive
title: "Articles"
date: 2014-06-02T12:26:34-04:00
modified: 2014-08-18T14:21:32-04:00
excerpt: "우선을 글을 쓰는데 목적이 있습니다. 채우고 채우다 보면.. 좀 더 잘 정리하는 날이 오겠지요."
---

<div class="tiles">
{% for post in site.categories.articles %}
  {% include post-grid.html %}
{% endfor %}
</div><!-- /.tiles -->

