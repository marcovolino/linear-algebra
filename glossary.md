---
layout: page
title: Glossary
---

{% for item in site.data.glossary %}
## {{ item.term }}

{{ item.definition }}
{% endfor %}
