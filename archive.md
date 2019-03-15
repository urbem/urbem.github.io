---
layout: page
title: Archive
permalink: archive/index.html
---

`Nothing is true,everything is permitted`

  {% if site.posts %}
  {% assign posts = site.posts | where:'layout', 'post' %}
  {% for post in posts %}
  {% capture this_year %}{{ post.date | date: "%Y" }}{% endcapture %}
  {% unless year == this_year %}

  {% if should_close %} </ul> {% endif %}
  {% assign year = this_year %}
  {% assign should_close = true %}

  <h3>Jahr {{ year }}</h3>
  <ul>

  {% endunless %}  

  <li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d.%m." }}</time> <a href="{{ post.url }}">{{ post.title }}</a></li>

  {% endfor %}

  {% if should_close %} </ul> {% endif %}

  {% endif %}
