---
layout: page
meta: nil
---
<!-- 자유형식 -->

<!-- 최근 글 -->
{% assign writes = site.entry_writes | default "" %}
{% assign reads = site.entry_reads | default "" %}
{% assign studies = site.entry_studies | default "" %}
{% assign plays = site.entry_plays | default "" %}
{% if writes == "" %}{% assign writes = "" | split: "" %}{% endif %}
{% if reads == "" %}{% assign reads = "" | split: "" %}{% endif %}
{% if studies == "" %}{% assign studies = "" | split: "" %}{% endif %}
{% if plays == "" %}{% assign plays = "" | split: "" %}{% endif %}
{% assign posts = writes | concat: reads | concat: studies | concat: plays %}
{% assign posts = posts | sort: "updated" | reverse | limit:7 %}
{% include list-posts.html %}
