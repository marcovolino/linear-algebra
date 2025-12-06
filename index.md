---
layout: home
---

{% assign posts = site.posts %}
{{posts}}

<ul>
{%- for post in posts -%}
  <li>
    <h3>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </h3>
  </li>
{%- endfor -%}
</ul>
