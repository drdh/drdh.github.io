<h2 id="publications" style="margin: 2px 0px -15px;">Publications</h2>

<div class="publications">
<ol class="bibliography">
<p>
  Most of my research is about robotics and agents. Some papers are <span class="highlighted">highlighted</span>.
</p>
{% for link in site.data.publications.main %}

<li >
<div class="pub-row {% if link.highlight %}highlighted{% endif %}">
  <div class="col-sm-3 abbr" style="position: relative;padding-right: 15px;padding-left: 15px;width: 60%; height: auto; display: flex; justify-content: center; align-items: center;">
    {% if link.video %} 
      <video autoplay muted loop playsinline class="teaser img-fluid z-depth-1" style="width: 100%; height: auto; aspect-ratio: auto; object-fit: cover;">
        <source src="{{ link.video }}" type="video/mp4">
        Your browser does not support the video tag.
      </video>
      {% if link.conference_short %} 
        <abbr class="badge">{{ link.conference_short }}</abbr>
      {% endif %}
    {% elsif link.image %} 
      <!-- <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width: auto; height: 100%; aspect-ratio: auto; object-fit: cover; text-align: center;"> -->
      <img src="{{ link.image }}" class="teaser img-fluid z-depth-1" style="width: 100%; height: auto; aspect-ratio: auto; object-fit: cover;">
      {% if link.conference_short %} 
        <abbr class="badge">{{ link.conference_short }}</abbr>
      {% endif %}
    {% endif %}
  </div>
  <div class="col-sm-9" style="position: relative;padding-right: 15px;padding-left: 20px;">
      <div class="title"><a href="{{ link.pdf }}">{{ link.title }}</a></div>
      <div class="author">{{ link.authors }}</div>
      <!-- <div class="periodical"><em>{{ link.conference }}</em> -->
      <div class="periodical"><em>TL;DR</em> {{ link.tldr }}
      </div>
    <div class="links">
      {% if link.pdf %} 
      <a href="{{ link.pdf }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">PDF</a>
      {% endif %}
      {% if link.code %} 
      <a href="{{ link.code }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Code</a>
      {% endif %}
      {% if link.page %} 
      <a href="{{ link.page }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Project Page</a>
      {% endif %}
      {% if link.poster %} 
      <a href="{{ link.poster }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Poster</a>
      {% endif %}
      {% if link.slides %} 
      <a href="{{ link.slides }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">Slides</a>
      {% endif %}
      {% if link.bibtex %} 
      <a href="{{ link.bibtex }}" class="btn btn-sm z-depth-0" role="button" target="_blank" style="font-size:12px;">BibTex</a>
      {% endif %}
      {% if link.notes %} 
      <strong> <i style="color:#e74d3c">{{ link.notes }}</i></strong>
      {% endif %}
      {% if link.others %} 
      {{ link.others }}
      {% endif %}
    </div>
  </div>
</div>
</li>
<br>

{% endfor %}

</ol>
</div>

<style>
  .highlighted {
      background-color: #ffffe0;
  }
</style>