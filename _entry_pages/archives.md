---
title: "#아카이브"
slug: archives
meta: null
---
<script async src="https://cse.google.com/cse.js?cx=b172018a73a4b4b15"></script>
<div class="gcse-searchbox-only"></div>

<div class="archives archives-type-terms archives-type-categories">
    <h1>{{ site.data.keywords.archives.types }}</h1>
    <ul class="list-terms list-categories">
        <li><a href="/reads">#{{ site.data.keywords.types.reads }}</a></li>
        <li><a href="/studies">#{{ site.data.keywords.types.studies }}</a></li>
        <li><a href="/writes">#{{ site.data.keywords.types.writes }}</a></li>
        <li><a href="/plays">#{{ site.data.keywords.types.plays }}</a></li>
    </ul>
</div>

{% assign posts = site.archive_categories %}
{% include list-posts-as-categories.html %}

{% assign posts = site.archive_tags %}
{% include list-posts-as-tags.html %}

{% assign posts = site.archive_years %}
{% include list-posts-as-years.html %}