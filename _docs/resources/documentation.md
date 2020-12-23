---
title: Documentation
---

# Documentation

The following templates have been custom designed to be deployed on [GitHub pages](https://pages.github.com/),
meaning directly from your master branch, the master branch "docs" folder, or
the "gh-pages" branch. To use any of these themes, just add the content there,
and then activate GitHub pages in your repository settings.

{% for theme in site.data.themes.documentation %}
<h2 id="{{ theme.title | slugify }}">{{ theme.title }}</h2>
<a href="{{ theme.url }}" target="_blank">
<img width="100%" src="{{ site.baseurl }}/assets/img/themes/documentation/{{ theme.image }}">
</a>
<div>
    <strong>Description:</strong> {{ theme.description }}
</div>
<hr>
{% endfor %}

All of these templates are open source, and available on GitHub, so if you see an issue
or would like to request a change, you can open an issue or pull request on the 
project board.

Would you like to see additional templates? Please [let us know]({{ site.repo }}/issues/new).
