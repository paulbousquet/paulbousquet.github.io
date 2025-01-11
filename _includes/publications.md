<div class="publications">
<ol class="bibliography">

{% for link in site.data.publications.main %}

<li>
<div class="pub-row">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;">
    {% if link.image %} 
    <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width=100;height=40%">
    {% if link.conference_short %} 
    <abbr class="badge">{{ link.conference_short }}</abbr>
    {% endif %}
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <div class="periodical"><em>{{ link.conference }}</em>
      </div>
    <div class="links">
   {% if link.abstract %}
   <button class="btn btn-sm z-depth-0" style="font-size:12px; margin-bottom: 0; padding: 2px 5px;" onclick="toggleAbstract(this)">[+] Abstract</button>
   <div class="abstract" style="display:none; margin-top: 2px; font-size:12px; padding-left: 10px;">
      <p style="margin: 0;">{{ link.abstract }}</p>
   </div>
   {% endif %}

   {% if link.pdf %} 
   <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
   {% endif %}
   {% if link.code %} 
   <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
   {% endif %}
   {% if link.page %} 
   <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
   {% endif %}
   {% if link.bibtex %} 
   <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
   {% endif %}
</div>

  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>

<script>
function toggleAbstract(button) {
    const abstract = button.nextElementSibling;
    if (abstract.style.display === 'none' || abstract.style.display === '') {
        abstract.style.display = 'block';
        button.textContent = '[-] Abstract';
    } else {
        abstract.style.display = 'none';
        button.textContent = '[+] Abstract';
    }
}
</script>
