---
layout: article
#permalink: /paperfaces/
title: "타이틀 입니다."
excerpt: "이 글의 대략적인 설명을 적어주세요. 주저리 주저리"
#modified: 2014-08-29T10:11:50-04:00    # 날자를 적어 주세요 없으면 파일 이름으로 알아서 됩니다. 
image: 
  thumb: # Grid에서 표시할때 노출되는?? 아닌가요?!
  teaser: # 
  feature: # 페이지 상단에 노출 되는 이미지 
category: articles
tags: [테그, tag, taaaag, 태애애애애그, 태 그, t a g]
---

사이트 기준이 아닌 글 기준으로 링크를 생성할 수 있습니다. 
<a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">링크는 알아서 잘 변환됩니다.</a>


글을 쓸때 가끔은 글자체가 좀 다를 필요도 있지요. [*다음(Daum)*](http://www.daum.net), 그렇지 않나요?!^^ --- bori ssak.
{:.shorten}

글을 쓸때 가끔은 글자체가 좀 다를 필요도 있지요. [*다음(Daum)*](http://www.daum.net), 그렇지 않나요?!^^ --- bori ssak.
{:.notice}


<nav class="toc toc-left">
  <ul>
    <li><h6>이글을 이렇게 써주세요. </h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 1</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 2</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 3</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 4</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 5</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 6</a></li>
    <li><h6>잘 쓰고 있다면 이렇게도 써도 됩니다. </h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 7</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 8</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 9</a></li>
    <li><h6>그리고.. 그리고.. </h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 10</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">글 11</a></li>
  </ul>
</nav>




In the spirit of openness I've decided to compile everything I've learned using [*Paper by FiftyThree*](http://www.fiftythree.com), into a series of tutorials and guides titled --- Mastering Paper.
{:.shorten}

<nav class="toc toc-left">
  <ul>
    <li><h6>Getting Started with Paper for iPad</h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Introduction and Tool Guide</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Moving the Zoom Loupe</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Drawing and Painting Basics</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Erasing and Correcting Mistakes</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Printing a Moleskine Book</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Mastering Mix</a></li>
    <li><h6>Step by Step Paper Tutorials</h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Trees and Grass</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Skies and Clouds</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Water and Waves</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Textures</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Skin and Faces</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">How to Draw Hair</a></li>
    <li><h6>Advanced Paper Techniques</h6></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">The Grid Method</a></li>
    <li><a href="{{ site.url }}{% post_url /articles/2014-01-01-templates %}">Contour Line Drawing</a></li>
  </ul>
</nav>

<div class="tiles tiles-right">
{% for post in site.categories.copycat-app-ui %}
  <article class="tile" itemscope itemtype="http://schema.org/Article">
    <a href="{{ post.url }}" title="{{ post.title }}" class="post-teaser">
      <img src="{{ site.url }}/images/preload-400.png" data-original="/images/{% if post.image.teaser %}{{ post.image.teaser }}{% else %}{{ site.teaser }}{% endif %}" class="load" alt="teaser" itemprop="image">
      <noscript><img src="/images/{% if post.image.teaser %}{{ post.image.teaser }}{% else %}{{ site.teaser }}{% endif %}" alt="teaser" itemprop="image"></noscript>
    </a>
    <h2 class="post-title" itemprop="name"><a href="{{ post.url }}">{{ post.title | remove: 'Mastering Paper by FiftyThree: ' | remove: 'Mastering Paper by 53: ' | remove: ' with Paper by 53' }}</a></h2>
    {% if post.date %}<p class="entry-date date published"><time datetime="{{ post.date | date: "%Y-%m-%d" }}" itemprop="datePublished">{{ post.date | date: "%B %d, %Y" }}</time></p>{% endif %}
    <p class="post-excerpt" itemprop="description">{{ post.excerpt | strip_html | truncate: 160 }}</p>
    </article><!-- /.tile -->
{% endfor %}
