---
layout: page
title: Categories
permalink: categories/index.html
---

Everything is the same, but you are not here, and I still am. In separation the one who goes away suffers less than the one who stays behind

<ul id="categories">
{% for category in site.categories %}
  <li id="{{ category | first }}"><h3>{{ category | first }}</h3>
    <ul>
    {% for posts in category %}
      {% for post in posts %}
        {% if post.title %}
        <li><time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%d.%m.%Y" }}</time> <a href="{{ post.url }}">{{ post.title }}</a></li>
        {% endif %}
      {% endfor %}
    {% endfor %}
    </ul>
  </li>
{% endfor %}
</ul>
