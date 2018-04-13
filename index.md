---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
#layout: home
layout: default
title: OToscano
---

<section class="section--first section--frontpage">
  <div class="section-title">
    <div class="container">
      <h1 class="textLogo textLogo--frontpage">
        {{ site.name }}
      </h1>
      <div class="postMeta-wrapper postMeta-wrapper--frontpage">
        <ul class="postMeta">
          <li class="postMeta-tagline">
            a writers corner 
          </li>
        </ul>
      </div>
    </div>
  </div>
</section>
<section class="section--postsWrapper">
  <div class="container">
    <div class="blockGroup">
      <ul class="blockGroup-list">
        {% for post in site.posts %}
          <li class="block">
            <div class="postArticle-wrapper">
              <article class="postArticle postArticle--short">
                {% if post.image.feature %}
                  <a href="{{ post.url }}">
                    <div class="postArticle-image desaturate" style="background-image:url('{{ post.image.feature | prepend: site.baseurl_featured_img }}')">
                    </div>
                  </a>
                {% else %}
                <a href="{{ post.url }}">
                  <div class="postArticle-image" style="background-image:url('{{site.baseurl}}assets/images/logo-black.svg')">
                  </div>
                </a>
                {% endif %}
                <a class="postArticle-title" href="{{ post.url }}">{{ post.title }}</a>
              </article>
              <div class="block-postMeta">{{ post.date | date_to_string }}</div>
            </div>
          </li>
        {% endfor %}
      </ul>
    </div>
  </div>
</section>
