---
layout: splash
permalink: /projects
read_time: false
header:
  overlay_color: "#5e616c"
  overlay_image: /assets/images/mm-home-page-feature.jpg
title: Projects
excerpt: >
  This is where you can find all the cool stuff we are working on, have worked on and will hopefully be working on!   
---
{% assign old_projects = site.projects | where: "type", "old" %}
{% assign current_projects = site.projects | where_exp: "proj", "proj.type == 'current'" | sort: 'year_start' | reverse%}


<h2>Current Projects</h2>

{% for project in current_projects %}
  <h3>
    <a href="{{ project.url }}">
      {{ project.acronyme }}
    </a>
  </h3>
  <b>Start year: </b>{{ project.year_start }}

  <b>Title: </b>{{ project.title }}
  
{% endfor %}

<h2>Archived Projects</h2>

{% for project in old_projects %}
  <h3>
    <a href="{{ project.url }}">
      {{ project.title }}
    </a>
  </h3>
{% endfor %}