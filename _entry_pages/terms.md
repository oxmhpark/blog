---
title: "#알기"
slug: terms
meta: null
---
> 지식에 관해 메모한다.

{% assign posts = site.entry_terms | default "" %}
{% if posts == "" %}{% assign posts = "" | split: "" %}{% endif %}
{% assign posts = posts | sort: "updated" | reverse %}
{% include list-posts.html %}
