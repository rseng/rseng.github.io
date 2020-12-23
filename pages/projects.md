---
layout: page
title: Projects
permalink: /projects
disable_editable: yes
---

# Projects

What is the rseng community working on? The following projects are a sample of 
in progress or completed projects, and each includes examples of how you might 
get involved. For any project, your contribution is hugely
encouraged!

<ul>
{% for project in site.projects %}<li><a href="#{{ project.title | slugify }}">{{ project.title }}</a></li>{% endfor %}
</ul>

<hr>

{% for project in site.projects %}
<h2 id="{{ project.title | slugify }}">{{ project.title }}</h2>
{{ project.description }}

{% if project.image %}<a href="{{ site.baseurl }}{{ project.url }}"><img style="width:100%; margin-top:40px;" src="{{ site.baseurl }}/assets/img/projects/{{ project.image }}"></a>{% endif %}

<a style="padding-top:200px" href="{{ site.baseurl }}{{ project.url }}"><button class="btn btn-primary">View</button></a>

<hr>

{% endfor %}

<br><br>

Do you have a commnity project that you want to add here? Please open an <a href="{{ site.repo }}/issues"><button class="btn btn-success btn-lg" >issue</button></a>.
