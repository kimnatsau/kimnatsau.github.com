---
layout: page
title: Мой блог
tagline: 
---
{% include JB/setup %}


#Посты
<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a> <p>{{post.description}}</p></li>
  {% endfor %}
</ul>




