---
layout: default
show_sidebar: false
---

<div class="columns is-multiline">

  <div class="column is-12">
    {{ page.content }}
  </div>

  {% assign sorted_tools = site.tools | sort:page.sort | reverse %}

  {% for tool in sorted_tools %}
  <div class="column is-6-desktop is-6-tablet">

    <a href="{{ tool.url | relative_url }}">

      <div class="card">

        {% if tool.image %}
        <div class="card-image">
          <figure class="image is-16by9">
            <img src="{{ tool.image }}" alt="{{ tool.title }}" />
          </figure>
        </div>
        {% endif %}
        <div class="card-content">

          <p class="title is-4">{{ tool.title }}</h2>
          <p class="subtitle is-4">{{ tool.subtitle | markdownify}}</p>  
          <p class="title is-5 has-text-right">{{ tool.date }}</p>

        </div>
      </div>

    </a>

  </div>
{% endfor %}
</div>

