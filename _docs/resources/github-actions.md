---
title: GitHub Actions
---

# GitHub Actions

The following GitHub actions might be helpful to generate content or automate things
for your GitHub repositories. If you need any help with customization or setting these
up, please don't hesitate to [reach out]({{ site.baseurl }}/support)

{% for action in site.data.templates.github-actions %}
<h2 id="{{ action.title | slugify }}">{{ action.title }}</h2>
<a href="{{ action.url }}" target="_blank">
{% if action.image %}<img width="100%" src="{{ site.baseurl }}/assets/img/templates/github-actions/{{ action.image }}">{% else %}Link {% endif %}
</a>
<div>
    <strong>Description:</strong> {{ action.description }}
</div>
<hr>
{% endfor %}

All of these actions are open source, and available on GitHub, so if you see an issue
or would like to request a change, you can open an issue or pull request on the 
project board.

{% include alert.html title="Would you like to request a Github Action?" type="info" content="Are you looking to automate something and need help?" %}

Please [let us know]({{ site.repo }}/issues/new).
