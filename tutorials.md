---
layout: page
title: My Brain Dump
subtitle: Random Stuff I Felt Like Writting
use-site-title: true
css: "/css/index.css"
bigimg:
  - "/img/bigimg/singapore-2018.JPG": "Singapore (2018)"
  - "/img/bigimg/singapore-2018-3.JPG": "Singapore (2018)"
  - "/img/bigimg/singapore-2018-2.JPG": "Singapore (2018)"
  - "/img/bigimg/phuket-thailand-2018.JPG": "Phuket, Thailand (2018)"
  - "/img/bigimg/phuket-thailand-2018-3.JPG": "Phuket, Thailand (2018)"
  - "/img/bigimg/phuket-thailand-2018-2.JPG": "Phuket, Thailand (2018)"
  - "/img/bigimg/chicago-illinois-2018.JPG": "Chicago, IL (2018)"
  - "/img/bigimg/chicago-illinois-2018-3.JPG": "Chicago, IL (2018)"
  - "/img/bigimg/chicago-illinois-2018-3.JPG": "Chicago, IL (2018)"
  - "/img/bigimg/shanghai-china-2018.JPG": "Shanhai, China (2018)"
  - "/img/bigimg/disneyland-california-2018-2.JPG": "Disneyland, California (2018)"
  - "/img/bigimg/disneyland-california-2018.JPG": "Disneyland, California (2018)"
  - "/img/bigimg/joshua-tree-callifornia.jpg": "Joshua Tree, California (2018)"
  - "/img/bigimg/cold-war-kids-anaheim-2019.jpg": "Cold War Kids - Anaheim, CA (2019)"
  - "/img/bigimg/muse-los-angeles-2019.jpg": "Muse - Los Angeles, CA (2019)"
  - "/img/bigimg/louisville-kentucky-2019.jpg": "Louisville, KY (2019)"
  - "/img/bigimg/big-bear-california-2019.JPG": "Big Bear, CA (2019)"
  - "/img/bigimg/csuf-2017.JPG": "Cal State Fullerton Shenanigans (2017)"
  - "/img/bigimg/austin-texas-2019.JPG" : "Austin, TX (2019)"
---

<div class="list-filters">
  <a href="/" class="list-filter">All posts</a>
  <span class="list-filter filter-selected">Tutorials</span>
  <a href="/tags" class="list-filter">Index</a>
</div>

<div class="posts-list">
  {% for post in site.tags.tutorial %}
  <article>
    <a class="post-preview" href="{{ post.url | prepend: site.baseurl }}">
	    <h2 class="post-title">{{ post.title }}</h2>
	
	    {% if post.subtitle %}
	    <h3 class="post-subtitle">
	      {{ post.subtitle }}
	    </h3>
	    {% endif %}
      <p class="post-meta">
        Posted on {{ post.date | date: "%B %-d, %Y" }}
      </p>

      <div class="post-entry">
        {{ post.content | truncatewords: 50 | strip_html | xml_escape}}
        <span href="{{ post.url | prepend: site.baseurl }}" class="post-read-more">[Read&nbsp;More]</span>
      </div>
    </a>  
   </article>
  {% endfor %}
</div>
