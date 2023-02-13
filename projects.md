---
title: Projects
permalink: /projects/
layout: default
---
# Projects

<style>
    table {
        width: 0%;
        max-width:100%;
        white-space:nowrap; 
        margin-bottom: 5px;       
        overflow-x: visible;
    }
    table, tbody, tr, td {
        border: none !important;
        border-collapse: collapse;

    }
    td {
        padding: 0px 8px 0px 0px !important;
    }
    h3 {
        margin-bottom: 0px !important;
    }
</style>

  {%- if site.projects.size > 0 -%}
    {%- if page.list_title -%}
      <h2 class="post-list-heading">{{ page.list_title }}</h2>
    {%- endif -%}
    <ul class="post-list">
      {%- assign date_format = "%Y %B" -%}
      {%- for post in site.projects reversed -%}
      <li>
        <h3 style="padding-bottom: 0px" class="post-link">
          <!-- <a class="" href="{{ post.url | relative_url }}"> -->
            {{ post.title | escape }}
          <!-- </a> -->
        </h3>
        <table>
            <tr>
                <td><span class="post-meta">{{ post.date | date: date_format }}</span></td>
            {%- for link in post.links -%}
                <td class="post-meta"><a href="{{ link.url }}">{{ link.name }}</a></td>
            {%- endfor -%}
            </tr>
        </table>
      </li>
      {%- endfor -%}
    </ul>
{% endif -%}