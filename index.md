---
layout: default
title: 홈
---

<!-- 최신 글 -->
<section>
  <h2>🆕 최신 글</h2>
  <ul class="post-list">
    {% assign recent_posts = site.posts | slice: 0, 5 %}
    {% for post in recent_posts %}
      <li>
        <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a>
        <span class="date">{{ post.date | date: "%Y-%m-%d" }}</span>
      </li>
    {% endfor %}
  </ul>
</section>

<!-- 카테고리별 보기 -->
<section>
  <h2>🗂️ 카테고리별 보기</h2>
  {% for category in site.categories %}
    <details>
      <summary>{{ category[0] }}</summary>
      <ul class="post-list">
        {% for post in category[1] %}
          <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
        {% endfor %}
      </ul>
    </details>
  {% endfor %}
</section>

<!-- 작성자별 보기 -->
<section>
  <h2>👤 작성자별 보기</h2>
  {% assign authors = site.posts | map: "author" | uniq %}
  {% for author in authors %}
    <details>
      <summary>{{ author }}</summary>
      <ul class="post-list">
        {% for post in site.posts %}
          {% if post.author == author %}
            <li><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></li>
          {% endif %}
        {% endfor %}
      </ul>
    </details>
  {% endfor %}
</section>
