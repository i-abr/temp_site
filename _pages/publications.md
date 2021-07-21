---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---

{% include base_path %}

{% if site.author.googlescholar %}
  You can also find my articles on <a href="{{ site.author.googlescholar }}">my Google Scholar profile</a>.
{% endif %}



<!-- {% for post in site.publications reversed %}
  {% include archive-single.html %}
{% endfor %} -->

<table style="width:100%;border:none;border-spacing:0px;border-collapse:separate;margin-right:auto;margin-left:auto;">
    {% for post in site.publications reversed %}
        {% for cat in post.categories %}
            {% if cat == 'research' %}
                <tr>
                    <td style="padding:6px;width:25%;vertical-align:middle; min-width:150px;">
                        <img src="{{post.image}}" alt="project image"
                            style="width:auto; height:auto; max-width:100%;" />
                    </td>
                    <td style="padding:20px;width:75%;vertical-align:middle;">
                        <strong style="font-size: 18px;">
                        {% if post.arxiv %}
                            <a href="{{post.arxiv}}">
                                {{post.title}}
                            </a>
                        {% elsif post.pdf %}
                            <a href="{{post.pdf}}">
                                {{post.title}}
                            </a>
                        {% else %}
                            {{post.title}}
                        {% endif %}
                        </strong>
                        <br>
                            {{post.authors}}
                        <br>
                            <em>{{post.venue}}</em>, {{ post.date | date: "%Y" }}
                        <br>
                        {% if post.project_page %}
                            <a href="{{post.project_page}}">project page</a>
                        {% endif %}
                        {% if post.code %}
                            <a href="{{post.code}}">code</a>
                        {% endif %}
                        <p style="text-align:justify">
                            {{ post.content }}
                        </p>
                    </td>
                </tr>
          {% endif %}
      {% endfor %}
  {% endfor %}
</table>