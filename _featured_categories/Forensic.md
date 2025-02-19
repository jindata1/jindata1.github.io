---
layout: page
title: Forensic
slug: forensic
permalink: /ctf/forensic/
description: >
  포렌식 관련 CTF 문제 풀이와 경험을 공유
  디지털 포렌식 분석과 데이터 복구 방법 등을 다룸
sitemap: false
---
{% assign posts = site.posts | where_exp: "post", "post.categories contains 'forensic'" %}
{% for post in posts %}
  <h2><a href="{{ post.url }}">{{ post.title }}</a></h2>
  <p>{{ post.excerpt }}</p>
{% endfor %}