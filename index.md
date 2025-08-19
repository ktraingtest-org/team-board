---
layout: home
title: "홈"
---

# 👋 팀 학습 공유 블로그에 오신 걸 환영합니다!

최신 학습 내용을 아래에서 확인하세요.  
카테고리별로 정리된 글을 통해 팀원들의 지식을 함께 나눠요.

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a> - {{ post.date | date: "%Y-%m-%d" }}
    </li>
  {% endfor %}
</ul>


