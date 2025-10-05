---
title: "#쓰기"
slug: writes
meta: null
---
> 내 것에 대해 메모한다.

{% assign posts = site.entry_journals | default "" %}
{% if posts == "" %}{% assign posts = "" | split: "" %}{% endif %}
{% assign posts = posts | sort: "updated" | reverse %}
{% include list-posts.html %}
