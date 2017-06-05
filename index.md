---
title: Navn på siden
layout: default
---
<main>
  <h1>{{ page.title }}</h1>
  <div class="dot-matrix"></div>
  <div class="page_header parallax-zoom-blur">
    <img src="{{ "/assets/img/04.jpg" | prepend: site.baseurl }}">
  </div>

  <div class="page_wrapper">
    <div class="container">

      <div class="row">
        <h1 class="hide-on-med-and-up">{{ page.title }}</h1>
      </div>

      <div class="row">
{% for post in site.posts %}
                <div class="col s12 m6 l4">
                  <a href="{{ post.url }}">
                    <div class="card">
                      <div class="card-image">
                        <img src="{{ site.baseurl }}/assets/img/{{ post.image }}">
                        <span class="card-title">{{ post.title }}</span>
                      </div>
                      <div class="card-content">
                        <p>{{ post.content | strip_html | truncatewords: 25 }}</p>
                        </div>
                      <div class="card-action">
                      <a href="{{ post.url }}">Læs mere...</a>
                      <span class="post-date">{{ post.date | date: "%b %-d, %Y" }}</span>
                      </div>
                    </div>
                  </a>
                </div>

{% endfor %}

      </div>

    </div>
  </div>
</main>
