---
layout: pages
title: John Doe
permalink: /forfatteren/
---
<main>
  <h1>{{ page.title }}</h1>
  <div class="dot-matrix"></div>
  <div class="page_header parallax-zoom-blur">
    <img src="{{ "/assets/img/03.jpg" | prepend: site.baseurl }}">
  </div>

  <div class="page_wrapper">
    <div class="container">
      <div class="row">

        <h1 class="hide-on-med-and-up">{{ page.title }}</h1>

        {% include auther.html %}

      </div>

      <div class="row">
        <h2>Uddybende beskrivelse her</h2>
        <p class="flow-text">
 Mauris vel tortor tincidunt, aliquam lacus vel, pellentesque ligula. Mauris varius consectetur libero, lobortis varius mi cursus nec. Pellentesque ac turpis in purus imperdiet viverra nec in lorem. Aliquam convallis tellus non arcu pretium, a aliquet sem finibus. Donec convallis id dui nec cursus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Fusce sed fringilla est, at facilisis est. Aenean congue nisl in pulvinar posuere.
        </p>
      </div>

    </div>
  </div>
</main>
