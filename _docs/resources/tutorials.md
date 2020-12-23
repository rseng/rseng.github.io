---
title: Tutorials
---

# Tutorials

The following tutorials can help you with data collection, version control, and packaging. 
These are created on request, so if you need any help with customization or setting these
up, please don't hesitate to [reach out]({{ site.baseurl }}/support)

## Data Collection

<ul>
{% for action in site.data.templates.data-collection %}
<li id="{{ action.title | slugify }}"><a href="{{ action.url }}" target="_blank"><strong>{{ action.title }}</strong></a>: {{ action.description }}</li>
{% endfor %}</ul>
<hr>

## Version Control

<ul>
{% for action in site.data.templates.version-control %}
<li id="{{ action.title | slugify }}"><a href="{{ action.url }}" target="_blank"><strong>{{ action.title }}</strong></a>: {{ action.description }}</li>
{% endfor %}</ul>
<hr>

## Packaging

<ul>
{% for action in site.data.templates.packaging %}
<li id="{{ action.title | slugify }}"><a href="{{ action.url }}" target="_blank"><strong>{{ action.title }}</strong></a>: {{ action.description }}</li>
{% endfor %}</ul>
<hr>


Please [let us know]({{ site.repo }}/issues/new) if you have a request for a new tutorial.
