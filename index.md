---
title: {{ site.title }}
---

<h1>{{ site.github.repository_nwo }}</h1>
[Issues]({{ site.github.issues_url }})
[Releases]({{ site.github.releases_url }})

<ul>
    {% for doc in site.pages %}
      <li>
        <a href="{{ doc.url }}">{{ doc.title }}</a>
        <blockquote>
            {{ doc.intro }}
        </blockquote>
      </li>
    {% endfor %}
</ul>

```json
{{ site.github }}
```