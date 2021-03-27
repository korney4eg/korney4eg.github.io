---
layout: page
title: Tasks
---

<section>
  {% if site.posts[0] %}

        <h3>Tasks:</h3>

    {%for post in site.posts %}
      {% unless post.next %}
        <ul>
      {% endunless %}
        <li>
          <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}
          </a>
        </li>
    {% endfor %}
    </ul>

  {% endif %}
</section>
