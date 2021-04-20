---
layout: page
title: Exercises
current_category: exercises
---
<section>
<h2>Exercises:</h2>
{% for phase in site.phases %}
{% assign phase_displayed = false %}
    {%for post in site.posts reversed %}
        {% if post.categories[0] == page.current_category and post.tags[0] == phase[0]%}
          {% if phase_displayed == false %}
            <h3>{{ phase[0] }}:"{{ phase[1] }}"</h3>
            {% assign phase_displayed = true %}
          {% endif %}
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
