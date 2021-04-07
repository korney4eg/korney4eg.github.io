---
layout: page
title: Tasks
current_category: tasks
---
<section>
<h2>Tasks:</h2>
{% for tag in site.tags %}
{% capture phase_name %}
<h3>{{ tag[0] | replace_regex: '_', ' '}}:</h3>
{% endcapture %}
    {%for post in tag[1] reversed %}
        {% if post.categories[0] == page.current_category %}
        {{ phase_name}} {% assign phase_name = '' %}
    <ul>
        <li>
          {% if post.active  %}
          <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}
          </a>
          {% else %}
            {{ post.title }}
          {% endif %}
        </li>
    </ul>
    {% endif %}
    {% endfor %}

{% endfor %}
</section>
