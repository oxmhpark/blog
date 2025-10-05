---
title: "#즐겨찾기"
slug: bookmarks
meta: null
---
> 내 것에 대해 메모한다.

{% assign posts = site.entry_journals | sort_natural: "date" | reverse %}
{% include list-posts.html %}
