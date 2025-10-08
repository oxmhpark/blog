---
title: "#즐겨찾기"
slug: bookmarks
meta: null
---
{% assign tags = site.archive_tags | default "" %}
{% if tags == "" %}{% assign tags = "" | split: "" %}{% endif %}
{% assign posts = tags | where_exp: "post", "post.bookmark == true" | sort: "title" %}
{% include list-posts-as-links.html %}
