---
title: Home
layout: page
---
## このサイトについて
このサイトは、大阪ハイテクノロジー専門学校の学生と講師で作った非公式のサイトです。授業の一環でGitHubの使い方を学ぶために作成しました。

- [2022年度生](/2022/)
- [2021年度生](/2021/)
- [2020年度生](/2020/)
- [2019年度生](/2019/)

<section class="post-list">
    {% for post in site.posts %}
      {% unless post.next %}
        <h2 class="category-title">{{ post.date | date: '%Y' }}</h2>
      {% else %}
        {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
        {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
        {% if year != nyear %}
          <h2 class="category-title">{{ post.date | date: '%Y' }}</h2>
        {% endif %}
      {% endunless %}
      <article class="post-item">
        <span class="post-meta date-label">{{ post.date | date: "%b %d" }}</span>
        <div class="article-title"><a class="post-link" href="{{ post.url | prepend: site.baseurl | prepend: site.url }}">{{ post.title }}</a></div>
      </article>
    {% endfor %}

</section>
