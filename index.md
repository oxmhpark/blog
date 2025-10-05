---
layout: page
meta: nil
---
<!-- 자유형식 -->

<!-- 최근 글 -->
{% assign writes = site.entry_writes | default "" %}
{% assign reads = site.entry_reads | default "" %}
{% assign terms = site.entry_terms | default "" %}
{% if writes == "" %}{% assign writes = "" | split: "" %}{% endif %}
{% if reads == "" %}{% assign reads = "" | split: "" %}{% endif %}
{% if terms == "" %}{% assign terms = "" | split: "" %}{% endif %}
{% assign posts = writes | concat: reads | concat: terms %}
{% assign posts = posts | sort: "updated" | reverse | limit:7 %}
{% include list-posts.html %}
