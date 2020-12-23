---
title: Software Checklist
disable_search: true
tags: 
 - badge
 - software
---

<style>
svg {
  cursor: pointer
}
</style>

# Software Checklist

<div id="app">

The following checklist is to ensure reproducible software. Check the points that apply, enter the name of your respository,
and then <span style="color:darkred">click the generate button</span>.

<br>
<blockquote class="markdown" style="display:none; overflow:hidden">
</blockquote>
<br>

<button class="btn btn-success" style="max-width:300px">Score: 
    <input class="form-control"
       placeholder="0"  style="background-color:transparent; width:50px; margin-left:5px; color:white; font-size:20px"
       type="text" v-model="score"><span>%</span></button>

<span style='float:right'>
{% include badges/software-checklist.svg extra='v-on:click="getCode()" title="Click to show markdown"'%}
</span>

{% for section in site.data.software-checklist.criteria %}<h2 id="{{ section.title | slugify }}">{{ section.title }}</h2>
<ul class="task-list">{% for item in section.items %}
  <li class="task-list-item" {% if item.comment %}title="{{ item.comment }}"{% endif %}><input id="{{ item.id }}" type="checkbox" class="task-list-item-checkbox" v-on:change="countPoints($event)"/><strong>{{ item.title }}:</strong> {{ item.description }} {% if item.url %}<a href="{{ item.url }}" target="_blank">[ref]</a>{% endif %}</li>{% endfor %}
</ul>{% endfor %}

<button v-on:click="getCode()" class="btn btn-warning" style="float:right">Generate</button>

<br>
<div class="form-group">
    <label>Your Repository or Software Name:</label>
    <input class="form-control" style="background-color:#F7F7F7"
       type="text" id="reponame" v-model="title">
</div>

<blockquote class="markdown" style="display:none; overflow:hidden">
</blockquote>

</div>

<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script>
new Vue({
  el: '#app',
  data: {
    // Current user score
    score: 0,
    points: 0,
    title: "username/reponame",

    // Must be same length as number of points
    colors: [{% for color in site.data.software-checklist.colors %}"{{ color }}"{% if forloop.last %}{% else %},{% endif %}{% endfor %}]
  },
  // The view will trigger these methods on click

  methods: {

    getCode: function() {
      // Get all of the unique ids
      var checked = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked')

      // Don't continue if no points checked!
      if (checked.length == 0) {
      $(".markdown").text("Please select at least one critera to generate a badge.");
      $(".markdown").show();
       return
      }

      // Ensure repository is entered
      if ((this.title == "username/reponame") || (this.title == "")) {
      $(".markdown").text("Don't forget to enter your repository name in the box at the bottom of the page.");
      $("#reponame").css("background-color", "tomato");
      $("#reponame").css("color", "white");
      $(".markdown").show();
       return
      }

      var ids = ""
      $.each(checked, function(i, e){
       ids = ids + $(e).attr('id') + ",";
      })
      ids = ids.replace(/(^,)|(,$)/g, "")

      // Prepare badge images
      var badgeColor = this.colors[this.points - 1]
      var badgeScore = Math.round(this.score) + "%25"
      var badgeUrl = "https://img.shields.io/badge/software%20checklist-" + badgeScore + "-" + badgeColor.replace("#", "");

      // Prepare badge link (summary page with badge and ids
      var badgeLink = "{{ site.url }}/{{ site.baseurl }}/docs/tools/software-checklist/badge?label=" + badgeScore + "&color=" + badgeColor + "&ids=" + ids + "&title=" + this.title

      var result = "[![" + badgeUrl + "](" + badgeUrl + ")](" + badgeLink + ")"
      $(".markdown").text(result);
      $(".markdown").show();

    },

    countPoints: function() {
      this.points = document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]:checked').length;
      this.score = (100 * (this.points / document.querySelectorAll('input.task-list-item-checkbox[type="checkbox"]').length)).toFixed(2);
      $('#svg-score').text(Math.round(this.score) + "%")
      $('#svg-color').attr("fill", this.colors[this.points - 1])
    }
  }
});
</script>
