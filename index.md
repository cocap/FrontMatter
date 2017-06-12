---
title: Navn på siden
layout: default
---
<main>
  <h1>{{ page.title }}</h1>
  <div class="dot-matrix"></div>
  <div class="page_header parallax-zoom-blur">
    <img src="http://i.imgur.com/DCfgKwb.jpg" alt="{{ page.title }}" title="{{ page.title }}">
  </div>

  <div class="page_wrapper">
    <div class="container">

      <div class="row">
        <h1 class="hide-on-med-and-up">{{ page.title }}</h1>
      </div>

      <div class="row">
{% for post in site.posts %}

                <div class="col s12 m6 l6">
                  <a href="/FrontMatter/{{ post.url }}">
                    <div class="card">
                      <div class="card-image">
                        {% assign images = post.content | split:"<img " %}
                          {% for image in images %}
                            {% if image contains 'src=' %}
                              {% assign imageMarkup = image | split:">" | first %}
                              <img {{ imageMarkup }}>
                            {% break %}
                          {% endif %}
                        {% endfor %}
                        <span class="card-title">{{ post.title }}</span>
                      </div>
                      <div class="card-content">
                        <p>{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
                      </div>

                      <div class="fixed-action-btn horizontal">
                        <a class="btn-floating btn-large indigo darken-4">
                          <i class="fa fa-share" aria-hidden="true"></i>
                        </a>
                        <ul>
                          <li><a class="btn-floating blue darken-4"><i class="fa fa-facebook" aria-hidden="true"></i></a></li>
                          <li><a class="btn-floating blue darken-4"><i class="fa fa-twitter" aria-hidden="true"></i></a></li>
                          <li><a class="btn-floating blue darken-4"><i class="fa fa-instagram" aria-hidden="true"></i></a></li>
                        </ul>
                      </div>

                    </div>
                  </a>
                </div>

{% endfor %}

      </div>

    </div>
  </div>
</main>
