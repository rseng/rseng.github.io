---
title: Software Checklist Badge
disable_editable: true
tags: 
 - badge
 - software
---

<style>
svg {
  cursor: pointer
}
.more  {
  display: none !important;
}
</style>

# Software Checklist Badge

<h2 id='title'></h2>

How is this repository doing for reproducible software? View the points below,
and [generate a badge](index) for your own repository. 

<div id="app">

<span style='float:right'>
{% include badges/software-checklist.svg extra='v-on:click="saveSvg()"'%}
</span>

{% for section in site.data.software-checklist.criteria %}<h2 id="{{ section.title | slugify }}">{{ section.title }}</h2>
<ul class="task-list">{% for item in section.items %}
  <li class="task-list-item" {% if item.comment %}title="{{ item.comment }}"{% endif %}><input id="{{ item.id }}" type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>{{ item.title }}:</strong> {{ item.description }} {% if item.url %}<a href="{{ item.url }}" target="_blank">[ref]</a>{% endif %}</li>{% endfor %}
</ul>{% endfor %}
</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
new Vue({
  el: '#app',
  data: {
    // Current user score
    score: 0,
    points: 0,
  },

  methods: {

    saveSvg: function() {

      // Get all of the unique ids
      var checked = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked')

      var ids = ""
      $.each(checked, function(e, i){
       ids = ids + $(i).attr('id') + ",";
      })
      ids = ids.strip(',');

      // Prepare badge image (dynamically generated svg)
      var badgeColor = this.colors[this.points - 1]
      var badgeScore = Math.round(this.score) + "%"
      var badgeUrl = "{{ site.url }}/{{ site.baseurl }}/docs/tools/software-checklist/badges/badge.svg?label= + " + badgeScore + "&color=" + badgeColor

      // Prepare badge link (summary page with badge and ids
      var badgeLink = "{{ site.url }}/{{ site.baseurl }}/docs/tools/software-checklist/badge?label= + " + badgeScore + "&color=" + badgeColor + "&ids=" + ids

      var result = "[![" + badgeUrl + "](" + badgeUrl + ")](" + badgeLink + ")"

    },

    countPoints: function() {
      this.points = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked').length;
      this.score = (100 * (this.points / document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]').length)).toFixed(2);
      $('#svg-score').text(Math.round(this.score) + "%")
      $('#svg-color').attr("fill", this.colors[this.points - 1])
    }
  }
});

(function() {

  function getUrlParams() {
    url = location.href;
    qs = url.split('+').join(' ');
    var params = {},
        tokens,
        re = /[?&]?([^=]+)=([^&]*)/g;
    while (tokens = re.exec(qs)) {
        params[decodeURIComponent(tokens[1])] = decodeURIComponent(tokens[2]);
    }
    return params;
  }

  params = getUrlParams()
  var ids = params['ids'].split(",")
  var title = params['title'] || ""
  for (i = 0; i < ids.length; i++) {
    document.getElementById(ids[i]).checked = true;
  }
  document.getElementById('title').innerHTML = title;
  
})();

</script>
