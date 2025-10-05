---
title: "#읽기"
slug: reads
meta: null
---
> 남의 것에 대해 메모한다.

{% assign posts = site.entry_objects | default "" %}
{% if posts == "" %}{% assign posts = "" | split: "" %}{% endif %}
{% assign posts = posts | sort: "updated" | reverse %}
{% include list-posts.html %}
