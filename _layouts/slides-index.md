---
layout: default
show_sidebar: false
---

<div class="columns is-multiline">

  <div class="column is-12">
    {{ page.content }}
  </div>

  {% assign sorted_slides = site.slides | sort:page.sort | reverse %}

  {% for slide in sorted_slides %}
  <div class="column is-6-desktop is-6-tablet">

    <a href="{{ slide.url | relative_url }}">

      <div class="card">

        {% if slide.image %}
        <div class="card-image">
          <figure class="image is-16by9">
            <img src="{{ slide.image }}" alt="{{ slide.title }}" />
          </figure>
        </div>
        {% endif %}
        <div class="card-content">

          <p class="title is-4">{{ slide.title }}</h2>
          <p class="subtitle is-4">{{ slide.subtitle | markdownify}}</p>  
          <p class="title is-5 has-text-right">{{ slide.date }}</p>

        </div>
      </div>

    </a>

  </div>
{% endfor %}
</div>

