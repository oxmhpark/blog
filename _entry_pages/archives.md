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

<div class="archives archives-type-terms archives-type-categories">
    <h1>{{ site.data.keywords.archives.categories }}</h1>
    <ul class="list-terms list-categories">
        {% for post in site.archive_categories %}
        <li><a href="{{ post.url }}">#{% include parts-title.html %}</a></li>
        {% endfor %}
    </ul>
</div>

<div class="archives archives-type-terms archives-type-tags">
    <h1>{{ site.data.keywords.archives.tags }}</h1>
    <ul class="list-terms list-tags">
        {% for post in site.archive_tags %}
        <li><a href="{{ post.url }}">#{% include parts-title.html %}</a></li>
        {% endfor %}
    </ul>
</div>

<div class="archives archives-type-terms archives-type-years">
    <h1>{{ site.data.keywords.archives.years }}</h1>
    <ul class="list-terms list-years">
        {% for post in site.archive_years %}
        <li><a href="{{ post.url }}">#{% include parts-title.html %}</a></li>
        {% endfor %}
    </ul>
</div>
