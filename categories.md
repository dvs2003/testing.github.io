---
title: 'Categories'
date: 2022-01-20T17:01:34+07:00
layout: default
banner_image: "../assets/images/banner-shape.png"
bodyClass: page-contact
---
{% include banner.html %}

<!-- start blog section -->
<section class="blog-section section-padding">
    <div class="container">
        <div class="row gutter-40 justify-content-center">
         {% for post in site.posts limit:6 %}
         <div class="col-lg-4 col-md-6">
            {% include post-card.html %}
         </div><!--  ./col -->
         {% endfor %}
        </div><!-- ./row -->
    </div><!--  ./container  -->
</section><!-- end blog section -->

<div class="container">
    <div class="row">
        {% for category in site.categories %}
        <div class="archive-group">
            {% capture category_name %}{{ category | first }}{% endcapture %}
            <div id="#{{ category_name | slugize }}"></div>
            <p></p>

            <h3 class="category-head">{{ category_name }}</h3>
            <a name="{{ category_name | slugize }}"></a>
            {% for post in site.categories[category_name] %}
            
            <article class="archive-item">
            <h4><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a></h4>
            </article>
            {% endfor %}
        </div>
        {% endfor %}
    </div>
</div>