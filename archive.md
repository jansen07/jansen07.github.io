---
layout: default
title: Archives
---

<div class="row section">
    <div class="col s12 m9">
      <div class="container">
        <h3 class="center">{{page.title}}</h3>
        <hr>
        <ul class="collection with-header">
          {% for post in site.posts %}
            {% unless post.next %}
              <li class="collection-header"><h5 class="scrollspy center" id="year{{ post.date | date: '%Y' }}">{{ post.date | date: '%Y' }}</h5></li>
            {% else %}
              {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
              {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
              {% if year != nyear %}
                <li class="collection-header"><h5 class="scrollspy center" id="year{{ post.date | date: '%Y' }}">{{ post.date | date: '%Y' }}</h5></li>
              {% endif %}
            {% endunless %}
            <li class = "collection-item">
                <time>
                {{ post.date | date:"%F" }} {{ post.date | date: "%a" }}.
                </time>
                <a class="title" href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
            </li>
          {% endfor %}
        </ul>
      </div>
    </div>
    <div class="col s12 m3 section" id="my-traget">
      <div class="section z-depth-2 pushpin-right" data-target="my-traget">
            <div class="container">
                <div>
                    Content
                </div>
                <ul>
                    {% assign counter = 0 %}
                        {% for post in site.posts %}
                          {% assign thisyear = post.date | date: "%Y" %}
                          {% assign prevyear = post.previous.date | date: "%Y" %}
                          {% assign counter = counter | plus: 1 %}
                          {% if thisyear != prevyear %}
                            <li><a data-scroll href="#year{{ post.date | date: '%Y' }}">{{ thisyear }} ({{ counter }})</a></li>
                            {% assign counter = 0 %}
                          {% endif %}
                        {% endfor %}
                </ul>
            </div>
</div>
    </div>

</div>


<script type="text/javascript">
    if ($('.pushpin-right').length) {
      $('.pushpin-right').each(function() {
        var $this = $(this);
        var $target = $('#' + $(this).attr('data-target'));
        $this.pushpin({
          top: 100
        });
      });
    }
</script>
