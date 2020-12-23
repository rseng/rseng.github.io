---
title: Google Cloud
---

# Google Cloud

The following Google Cloud templates might be helpful to get you started to deploy
something on app engine, or run a workflow. If you need any help with customization or setting these
up, please don't hesitate to [reach out]({{ site.baseurl }}/support)

{% include alert.html title="Stanford Minimum Security Requirements" type="warning" content="We take security very seriously at Stanford. Make sure that your application meets the <a href='/rse-services/docs/resources/risk-classification#pancakes-templates'>Stanford Minimum Security Standards</a> before deployment." %}

{% for action in site.data.templates.google-cloud %}
<h2 id="{{ action.title | slugify }}">{{ action.title }}</h2>
<a href="{{ action.url }}" target="_blank">
{% if action.image %}<img width="100%" src="{{ site.baseurl }}/assets/img/templates/google-cloud/{{ action.image }}">{% else %}Link {% endif %}
</a>
<div>
    <strong>Description:</strong> {{ action.description }}
</div>
<hr>
{% endfor %}

## Use Cases

### 1. I want to deploy a shiny app

If you have a [shiny app](https://shiny.rstudio.com/) that needs more than the 25 free hours on [shinyapps.io](https://www.shinyapps.io/), you might
be interested to know that Google Cloud has a [ready-to-go template](https://console.cloud.google.com/marketplace/details/rstudio-launcher-public/rstudio-connect-enterprise-1000-users) for R and Python applications.

All of these templates are open source, and available on GitHub, so if you see an issue
or would like to request a change, you can open an issue or pull request on the 
project board.

Please [let us know]({{ site.repo }}/issues/new).
