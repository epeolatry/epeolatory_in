---
layout: default
title: My Works
---
<div class='o-wrapper'>
  <div class="flex-sections" style="text-align: center;">
    <div class="flex-row">
      <h2>Editings</h2>
    </div>
  </div>
  <div class='o-grid js-grid'>
    {% for post in site.data.editings %}
      {% include post-card-alt.html %}
    {% endfor %}
  </div>

  <div class='o-grid'>
    <div class='o-grid__col o-grid__col--full'>
      <hr>
    </div>
  </div>
  <div class='o-grid'>
    {% include instagram.html %}
  </div>

  <div class="flex-sections" style="text-align: center;">
    <div class="flex-row">
      <h2>Beta Reads</h2>
    </div>
  </div>
  <div class='o-grid js-grid'>
    {% for post in site.data.beta-reads %}
      {% include post-card-alt.html %}
    {% endfor %}
  </div>

  <div class='o-grid'>
    <div class='o-grid__col o-grid__col--full'>
      <hr>
    </div>
  </div>
  <div class='o-grid'>
    {% include instagram.html %}
  </div>
</div>
