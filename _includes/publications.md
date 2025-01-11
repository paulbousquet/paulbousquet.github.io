<!-- <h3 id="publications" style="margin: 2px 0px -15px;">Working Papers</h3> -->

<h3 id="publications" style="margin: 2px 0px -15px;"></h3>

<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 0px;">
      <!-- <div class="title"><a>{{ link.title }}</a></div> -->
      <div class="title"><a href="{{ link.draft }}">{{ link.title }}</a></div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
      {% if link.authors or link.abstract %}
        <div class="author">
        {% if link.authors %} 
          {{ link.authors }}
        {% endif %}
              {% if link.draft %} 
           <a href="{{ link.draft }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Draft</a>
      {% endif %}
        {% if link.abstract %} 
          <button id="{{ link.id }}" onClick="reply_click()" class="accordion"> Abstract </button>
        {% endif %}
        </div>
      {% endif %}
      {% if link.others %} 
        {{ link.others }}
      {% endif %}
      <div id="{{ link.id }}" class="panel" style="background-color: #F1F1F1; color: #666; padding: 10px;">
    {{ link.abstract }}
    </div>
    </div>
  </div>
</div>
</li>

<br>

{% endfor %}

</ol>
</div>
