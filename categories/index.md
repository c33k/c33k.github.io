---
layout: default
permalink: /categories/
title: Categories
bgContrast: dark
bgGradientOpacity: darker
---

<article class="postWrapper">
  <section class="section--first section--frontpage section--categories" id="categories-title">
    <div class="section-title">
        <div class="container">
        <h1 class="textLogo textLogo--frontpage">
            {{ page.title }}
        </h1>
        <div class="postMeta-wrapper postMeta-wrapper--frontpage">
            <ul class="postMeta">
            <li class="postMeta-tagline">
                ARCHIVE OF POSTS
            </li>
            </ul>
        </div>
        </div>
    </div>
  </section>
  <section class="section--last">
    <div class="container container--content">
      <div class="content-body">
        {% for category in site.categories reversed%}
            <div>
                {% capture category_name %}{{ category | first }}{% endcapture %}
                {% capture base_url %}{{ site.metainfo.baseurl }}{% endcapture %}
                <div id="#{{ category_name | slugize }}"></div>
                <h4 class="category-head">{{ category_name }}</h4>
                <a name="{{ category_name | slugize }}"></a>
                {% for post in site.categories[category_name] %}
                    <li><span>{{ post.date | date_to_string }}</span> &nbsp; <a href="{{ post.url }}">{{ post.title }}</a></li>
                {% endfor %}
            </div>
            {% endfor %}
      </div>
    </div>
  </section>
</article>
<hr/>
{% include subscribe.html %}
{% include footer.html %}

