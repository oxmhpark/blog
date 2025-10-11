NEMORIUM.NET
============

> [옥수박](https://github.com/oxmhpark)의 개인 블로그.

# 적용 기술

| 항목   | 제품            | 링크                                          |
|--------|-----------------|-----------------------------------------------|
| 플랫폼 | 깃허브 페이지스 | <https://pages.github.com>                    |
| 블로그 | 지킬            | <https://jekyllrb.com>                        |
| 댓글   | giscus          | <https://giscus.app>                          |
| 검색   | GPSE            | <https://programmablesearchengine.google.com> |
| 글꼴   | Freesentation   | <https://freesentation.blog>                  |

# 고정 페이지

관리 목적이 아니라면 추가할 일이 없을 것이다.

| 항목      | 소스 경로                                                                                            |
|-----------|------------------------------------------------------------------------------------------------------|
| 첫 페이지 | [`/index.md`](https://github.com/oxmhpark/blog/tree/main/index.md)                                   |
| 아카이브  | [`/_entry_pages/archives.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/archives.md)   |
| 즐겨찾기  | [`/_entry_pages/bookmarks.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/bookmarks.md) |
| 소개      | [`/_entry_pages/about.md`](https://github.com/oxmhpark/blog/tree/main/_entry_pages/about.md)         |
| RSS 피드  | [`/feed.xml`](https://github.com/oxmhpark/blog/tree/main/feed.xml)                                   |
| 사이트맵  | [`/sitemap.xml`](https://github.com/oxmhpark/blog/tree/main/sitemap.xml)                             |

# 분류 방침

대분류를 제외한 나머지 범주는 복수설정이 가능하다.

| 범주   | 기준                             | 설정                         | 아카이브 경로                                                                             |
|--------|----------------------------------|------------------------------|-------------------------------------------------------------------------------------------|
| 대분류 | 행위의 종류                      | 폴더 분리                    | `대분류` 단락에서 기술                                                                    |
| 중분류 | 게시 목적(프로젝트)              | `categories` 프론트매터 지정 | [`/_archive_categories/`](https://github.com/oxmhpark/blog/tree/main/_archive_categories) |
| 소분류 | 구체적 소재[^tag-assign-policy]  | `tags` 프론트매터 지정       | [`/_archive_tags/`](https://github.com/oxmhpark/blog/tree/main/_archive_tags)             |
| 연도   | 관련된 연도[^year-assign-policy] | `years` 프론트매터 지정      | [`/_archive_years/`](https://github.com/oxmhpark/blog/tree/main/_archive_years)           |

[^tag-assign-policy]: 예를 들어, '인물'은 부적절하고 '시로 마사무네'는 적절하다.
[^year-assign-policy]: 게시물이 작성·수정된 연도, 내용 안에서 다뤄지는 연도.

## 대분류

| 콜렉션 이름 | 설정                  | 폴더 경로                                                                        |
|-------------|-----------------------|----------------------------------------------------------------------------------|
| 읽기        | 텍스트 정보·단순 요약 | [`/_entry_reads/`](https://github.com/oxmhpark/blog/tree/main/_entry_reads/)     |
| 알기        | 텍스트 평가·주제 연구 | [`/_entry_studies/`](https://github.com/oxmhpark/blog/tree/main/_entry_studies/) |
| 쓰기        | 사설·창작             | [`/_entry_writes/`](https://github.com/oxmhpark/blog/tree/main/_entry_writes/)   |
| 놀기        |                       | [`/_entry_plays/`](https://github.com/oxmhpark/blog/tree/main/_entry_plays/)     |

# 운영 방침

* 이미지 업로드, 글감과 토막글 저장은 [메모장](https://memo.nemorium.net)을 이용한다.
* 제목·대사 인용에는 겹낫표(『』)를, 소제목·지문 인용에는 홑낫표(「」)를 쓴다.
* 문서 구조를 단순하게 유지하고 주요 갱신이력을 남긴다. (`lastmod` 프론트매터)
* 댓글 기능을 통한 소통에 과한 비용을 치르지 않도록 주의한다.

[memo]: https://memo.nemorium.net/@oxmhpark