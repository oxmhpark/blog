---
title: 관리 및 운영 지침
slug: 관리-및-운영-지침
layout: page
---
NEMORIUM.NET
============

[개인 블로그 프로젝트](https://github.com/oxmhpark/blog) 개발 및 운영에 대한 내부 지침.

# 적용 기술

| 항목   | 제품            | 링크                                          |
|--------|-----------------|-----------------------------------------------|
| 플랫폼 | 깃허브 페이지스 | <https://pages.github.com>                    |
| 블로그 | 지킬            | <https://jekyllrb.com>                        |
| 댓글   | giscus          | <https://giscus.app>                          |
| 검색   | GPSE            | <https://programmablesearchengine.google.com> |
| 글꼴   | Freesentation   | <https://freesentation.blog>                  |

# 고정 페이지

관리 목적이 아니라면 추가하지 않는다.

| 항목      | 소스 경로                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| 첫 페이지 | [`/index.md`](https://github.com/oxmhpark/blog/tree/main/index.md)                                   |
| 아카이브  | [`/_entry_pages/archives.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/archives.md)   |
| 즐겨찾기  | [`/_entry_pages/bookmarks.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/bookmarks.md) |
| 소개      | [`/_entry_pages/about.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/about.md)         |
| RSS 피드  | [`/feed.xml`](https://github.com/oxmhpark/blog/tree/main/feed.xml)                                   |
| 사이트맵  | [`/sitemap.xml`](https://github.com/oxmhpark/blog/tree/main/sitemap.xml)                             |

# 게시물 분류 방침

대분류를 제외한 나머지 범주는 복수 설정이 가능하다.

| 범주      | 기준                             | 설정                         | 아카이브 경로                                                                             |
|-----------|----------------------------------|------------------------------|-------------------------------------------------------------------------------------------|
| 대분류    | 행위의 종류                      | 폴더 분리                    | `대분류` 단락에서 기술                                                                    |
| 중분류    | 행위의 목적(프로젝트)            | `categories` 프론트매터 지정 | [`/_archive_categories/`](https://github.com/oxmhpark/blog/tree/main/_archive_categories) |
| 소분류    | 구체적 소재                      | `tags` 프론트매터 지정       | [`/_archive_tags/`](https://github.com/oxmhpark/blog/tree/main/_archive_tags)             |
| 연도 분류 | 관련된 연도[^year-assign-policy] | `years` 프론트매터 지정      | [`/_archive_years/`](https://github.com/oxmhpark/blog/tree/main/_archive_years)           |

[^year-assign-policy]: 게시물이 작성·수정된 연도, 내용 안에서 다뤄지는 연도.

## 대분류

이 체계는 바뀔 가능성이 낮다.

| 콜렉션 이름 | 설정                  | 폴더 경로                                                                        |
|-------------|-----------------------|----------------------------------------------------------------------------------|
| 읽기        | 텍스트 정보·단순 요약 | [`/_entry_reads/`](https://github.com/oxmhpark/blog/tree/main/_entry_reads/)     |
| 알기        | 텍스트 평가·주제 연구 | [`/_entry_studies/`](https://github.com/oxmhpark/blog/tree/main/_entry_studies/) |
| 쓰기        | 사설·창작             | [`/_entry_writes/`](https://github.com/oxmhpark/blog/tree/main/_entry_writes/)   |
| 놀기        |                       | [`/_entry_plays/`](https://github.com/oxmhpark/blog/tree/main/_entry_plays/)     |

## 중분류

구체적인 프로젝트에 대응한다. `인문학 입문` `기기 관리` `개발 일지` 등 운영 계획에 따라 얼마든지 늘어날 수 있다.

## 소분류

소분류로는 구체적 인명, 작품명, 지명, 사건 이름 등을 지정한다. 그것들을 묶는 상위 개념은 사용하지 않는다. 몇 가지 예를 들어 보면:

| 소분류              | 타당성 | 비고                                                                                     |
|---------------------|--------|------------------------------------------------------------------------------------------|
| 인물                | ×      | 검색에는 도움이 되겠지만, 지나치게 폭넓다.                                               |
| 시로 마사무네       | ○      | 작가의 이름; 소속 게시물에서 이 사람의 행적에 대해 논할 수 있다.                         |
| 운영체제            | △      | 기술 분야의 특성상 운영체제라는 개념에 대해 논할 수 있다.                               |
| 윈도우즈            | ○      | 운영체제의 이름.                                                                         |
| 윈도우즈 11         | △      | 운영체제의 특정 버전에 대해 반복적으로 논할 수 있다.                                     |
| 키보드 펌웨어       | ×      | 지나치게 폭넓다.                                                                         |
| QMK (앱) | ○      | 구체적인 펌웨어 이름; 소속 게시물에서 이 제품의 정보, 용법, 사례 연구 등을 다룰 수 있다. |
| 인문학              | ×      | `인문학 입문`이라는 중분류(프로젝트)로 취급하는 것이 타당하다.                           |
| 인간과 기호         | ○      | 책 제목; 소속 게시물에서 이 책의 특정 판본, 장, 절, 요약을 다룰 수 있다.                 |

개인 블로그인 만큼 방문객의 검색 편의성보다는 관리 편의성을 중시하기로 한다. 예를 들어, 윈도우즈 11의 특정 기능에 대해 다루는 게시물에는 `윈도우즈 11` 소분류만을 지정한다. 같은 상황에서 `운영체제` `윈도우즈` `윈도우즈 11` 소분류를 모두 지정하는 방식은 오탈자·누락 가능성이 크고, 동일 원칙을 다른 소분류에도 적용하게 되면서 관리 부담도 증가하기 때문이다.

동음이의어와 축약어를 소분류로 지정하는 경우에는 `소분류 이름 (종류)` 형식으로 작명한다. 예를 들어, `엑스 (문자)` `엑스 (만화)` `IBM (기업)` `HAL (인물)` `QMK (앱)` 등.[^ambiguous-text] `Jekyll`의 특성 상, 기존 소분류에 새로운 동음이의어가 발생하는 경우에는 수작업으로 교정해야 한다.

[^ambiguous-text]: 저작물의 경우에는 `저작물 제목 (창작자)` 형식을 따른다. 동일 창작자가 동명의 저작물을 여러 번 출판한 경우에는 게시물 제목에 버전을 명시한다. 

# 운영 방침

* 이미지 업로드·글감 수집·토막글 저장은 [메모장](https://memo.nemorium.net)을 이용한다.
* 게시물 작성은 [옵시디언](https://obsidian.md)을 이용하고, 저장소에는 최종본만 반영한다.
* 논거를 추가하는 정도라면 서두에 주요 갱신 이력을 남기고, 논조에 변화가 있다면 별도의 게시물로 분리한다.
* 중복 링크를 만들지 않는다. (특히 대분류·중분류·소분류·연도 분류로 지정된 단어가 본문에 재등장하는 경우)
* 텍스트 제목·제품 이름·사건 이름·대사 인용에는 겹낫표(『』)를, 소제목·지문 인용에는 홑낫표(「」)를 쓴다.
* 인명·국가명·지명은 기호로 감싸거나 강조하지 않는다.
* 앱 이름·용어·API·코드 조각은 코드 블록으로 감싼다.
* 고유명사는 한글 표기를 기본으로 삼되[^localization-policy], 첫 인용에는 원문을 병기한다.[^internationalization-policy]
* `<h3>` 이하의 섹션 사용을 자제한다.
* 반복 응답 또는 장문의 응답이 필요한 경우에는 그 내용을 게시물로 승격시킨다.
* 모든 댓글에 응답할 의무는 없다.[^communication-policy]
* 광고·스팸·사생활 침해성 댓글은 통보 없이 삭제한다.

[^localization-policy]: 순우리말로 대체할 필요는 없다.
[^internationalization-policy]: 이미 소분류로 지정된 경우에는 생략한다.
[^communication-policy]: 소통이 주된 운영목적은 아니기 때문이다.
