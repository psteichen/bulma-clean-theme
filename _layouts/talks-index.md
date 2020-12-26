---
layout: default
show_sidebar: false
---

{{ content }}

<div class="columns is-multiline">
  <div class="column is-12">
    {% include pagination.html %}
  </div>
  {% for talk in paginator.posts %}
  <div class="column is-6">
    {% include haikudeck-embed.html deck=talk.deck %}
  </div>
  {% endfor %}
  <div class="column is-12">
    {% include pagination.html %}
  </div>
</div>
