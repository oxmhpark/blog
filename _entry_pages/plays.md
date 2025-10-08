---
title: "#놀기"
layout: type
collection: entry_plays
slug: plays
meta: null
---
{% assign posts = site.entry_plays | default "" %}
{% if posts == "" %}{% assign posts = "" | split: "" %}{% endif %}
{% assign posts = posts | sort: "updated" | reverse %}
{% include list-posts.html %}
