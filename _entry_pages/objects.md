---
title: "#즐겨찾기"
slug: bookmarks
meta: null
---
> 남의 것에 대해 메모한다.

{% assign posts = site.entry_objects | sort_natural: "date" | reverse %}
{% include list-posts.html %}
