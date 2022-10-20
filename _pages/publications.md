---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% if author.googlescholar %}
  You can also find my articles on <u><a href="{{author.googlescholar}}">my Google Scholar profile</a>.</u>
{% endif %}

<!-- {% include base_path %}

{% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %} -->


<ul>
    {% assign pub_list = site.publications.publications | sort: 'Publication Year' | group_by: 'Publication Year' | reverse %}

    {% for group in pub_list %}

        {% assign year = group.name | to_integer %}

        <h3>{{ year }}</h3>
        {% for publi in group.items %}
            <!-- {%- include publication.html -%} -->
            <p>{{publi}}</p>
        {% endfor %}

    {% endfor %}
</ul>