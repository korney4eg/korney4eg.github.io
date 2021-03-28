---
layout: page
title: Tasks
---
<section>
<h2>Tasks:</h2>
{% for tag in site.tags %}
<h3>{{ tag[0] | replace_regex: '_', ' '}}:</h3>
    {%for post in tag[1] reversed %}
    <ul>
        <li>
	{% if post.active %}
          <a href="{{ post.url | prepend: site.baseurl | replace: '//', '/' }}">
            {{ post.title }}
          </a>
    {% else %}
            {{ post.title }}
    {% endif %}
        </li>
    </ul>
    {% endfor %}

{% endfor %}
</section>
