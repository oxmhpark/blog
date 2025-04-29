---
layout: page
meta: nil
---
<!-- 자유형식 -->

<!-- 최근 글 -->
{% assign posts = site.entry_journals | sort: 'updated' | reverse | limit:7 %}
{% include list-posts-item.html %}
