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
        <li><a href="/writes">#{{ site.data.keywords.types.writes }}</a></li>
        <li><a href="/reads">#{{ site.data.keywords.types.reads }}</a></li>
        <li><a href="/terms">#{{ site.data.keywords.types.terms }}</a></li>
        <li><a href="/links">#{{ site.data.keywords.types.links }}</a></li>
    </ul>
</div>

{% assign categories = site.archive_categories %}
{% include list-categories.html %}

{% assign tags = site.archive_tags %}
{% include list-tags.html %}

{% assign years = site.archive_years %}
{% include list-years.html %}