---
layout: page
meta: nil
---
<!-- 자유형식 -->

<!-- 최근 글 -->
{% assign journals = site.entry_journals | default "" %}
{% assign objects = site.entry_objects | default "" %}
{% assign terms = site.entry_terms | default "" %}
{% if journals == "" %}{% assign journals = "" | split: "" %}{% endif %}
{% if objects == "" %}{% assign objects = "" | split: "" %}{% endif %}
{% if terms == "" %}{% assign terms = "" | split: "" %}{% endif %}
{% assign posts = journals | concat: objects | concat: terms %}
{% assign posts = posts | sort: "updated" | reverse | limit:7 %}
{% include list-posts.html %}
