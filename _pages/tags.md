---
layout: content
title: Tags
permalink: /tags/
---
<ul class="tag-cloud">
{% for tag in site.tags %}
<!-- <span style="font-size: {{ tag | last | size | times: 70 | divided_by: site.tags.size | plus: 70  }}%"> -->
<span style="font-size: medium">
<a href="#{{ tag | first | slugize }}">
{{ tag | first }}
    </a> &nbsp;&nbsp;
</span>
{% endfor %}
</ul>

<div id="archives">
{% for tag in site.tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <br>
    <h4 id="#{{ tag_name | slugize }}">{{ tag_name }}</h4>  
    <a name="{{ tag_name | slugize }}"></a>  
      {% for post in site.tags[tag_name] %}  
      <article class="archive-item">  
          <h4><small><a href="{{ root_url }}{{ post.url }}">{{post.title}}</a> {{ post.date | date: "%b %-d, %Y" }}</small></h4>
    </article>
    {% endfor %}
  </div>
{% endfor %}
    </div>
