---
title: Navn på siden
layout: default
images: "http://i.imgur.com/DCfgKwb.jpg"
---
<main>
  <h1 class="desktop">{{ page.title }}</h1>
  <div class="dot-matrix"></div>
  <div class="page_header parallax-zoom-blur">
    <img src="http://i.imgur.com/DCfgKwb.jpg" alt="{{ page.title }}" title="{{ page.title }}">
  </div>

  <div class="page_wrapper">
    <div class="container">

      <div class="row">
{% for post in site.posts %}

                <article class="col s12 m6 l6">
                  <a href="{{ post.url | prepend: site.baseurl }}">
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
                        <span class="card-title truncate">{{ post.title }}</span>
                      </div>
                      <div class="card-content">
                        <p>{{ post.desc | truncatewords: 35 }}</p>
                      </div>

                      <div class="fixed-action-btn horizontal">
                        <a href="{{ post.url | prepend: site.baseurl }}" class="btn-floating btn-large z-depth-2 blue-grey lighten-3">
                          <i class="fa fa-share" aria-hidden="true"></i>
                        </a>
                        <ul>
<li>
<a class="btn-floating blue darken-4" href="https://www.facebook.com/dialog/feed?app_id=488375674843191&redirect_uri={{post.url | prepend: site.siteurl}}&link={{post.url | prepend: site.siteurl}}&picture={{post.images}}&caption={{post.title}}&description=This%20is%20the%20description" target="blank" target="blank">
<i class="fa fa-facebook" aria-hidden="true"></i>
</a>
</li>
<li>
<a class="btn-floating blue" href="http://twitter.com/intent/tweet?status=[{{post.title}}]+[{{post.url | prepend: site.siteurl}}]" target="blank">
<i class="fa fa-twitter" aria-hidden="true"></i>
</a>
</li>
                        </ul>
                      </div>

                    </div>
                  </a>
                </article>

{% endfor %}

      </div>

    </div>
  </div>
</main>
