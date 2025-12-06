---
layout: home
---

{% assign posts = site.posts %}
<ul class="post-list">
{%- for post in posts -%}
  <li>
    <h3>
    <a class="post-link" href="{{ post.url | relative_url }}">
      {{ post.title | escape }}
    </a>
    </h3>
  </li>
{%- endfor -%}
</ul>
