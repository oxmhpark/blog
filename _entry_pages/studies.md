---
title: "알기"
layout: type
collection: entry_studies
slug: studies
meta: null
---
{% assign posts = site.entry_studies | default "" %}
{% if posts == "" %}{% assign posts = "" | split: "" %}{% endif %}
{% assign posts = posts | sort: "updated" | reverse %}
{% include list-posts.html %}
