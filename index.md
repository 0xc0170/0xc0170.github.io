---
layout: page
title: Martin Kojtal's webpage
tagline: Notes, code snippets, projects
---
{% include JB/setup %}

<div class="container-fluid">
  <div class="row-fluid">
      <div class="span9">
          <ul >
              {% for post in site.posts limit:8 %}
              <h3><a class="post_link" href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></h3>
              <p>
                {{ post.content | strip_html | truncatewords:75}}
                <a href="{{ post.url }}"><strong> Read more.</strong></a><br/>
              </p>
              <p>
                <strong>
                    {{ post.date | date_to_string }}
                </strong>
                | Category: {{ post.categories }}
              </p>
              {% if forloop.last %}
              {% else %}
                <hr>
              {% endif %}
              {% endfor %}
          </ul>
          <div> For older posts, look at <a href="/pages/nav/archive.html">Archive</a></div>
      </div>
      <!--
      <div class="span2 offset 1">
          <h4>Categories</h4>
          <ul class="tag_box inline">
              {% assign categories_list = site.categories %}
              {% include JB/categories_list %}
          </ul>
      </div>
      -->
  </div>
</div>




