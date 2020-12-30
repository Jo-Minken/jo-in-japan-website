---
layout: default
permalink: /category/
title: 目錄
display: false
---


<div id="archives" id="#{{ category_name | slugize }}">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}

    <div class="arhive-head">
      <div class="container">
        <h1 class="archive-title">{{ category_name }}</h1>
      </div>
    </div>
    <a name="{{ category_name | slugize }}"></a>
    {% for post in site.categories[category_name] %}
    <!-- <article class="archive-item">
      <h4><a href="{{ site.baseurl }}{{ post.url }}">{% if post.title and post.title != "" %}{{post.title}}{% else %}{{post.excerpt |strip_html}}{%endif%}</a></h4>
    </article> -->
    {% include article-content.html %}
    {% endfor %}
  </div>
{% endfor %}
</div>