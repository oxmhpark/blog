---
published: true
title: "Silver: 비트맵 스타일 CJK 글꼴"
slug: "silver-bitmap-style-cjk-font"
date: 2025-02-21 00:00:00 +0900
years:
  - 2025
categories:
  - 게임 개발
tags:
  - 문자
  - 전산화
links:
  - Silver 글꼴
excerpt: "개인 프로젝트에 「실버 Silver」 글꼴을 사용하기로 했다. 글꼴 하나로 CJK 문자를 커버할 수 있는지·섞어 썼을 때 잘 어울리는지·픽셀 아트 프로젝트에 적합한지 따위를 모두 고려하면 선택지가 많지 않은데, 「실버」는 그런 요구에 부응할 뿐 아니라 게임과 관련된 특수문자를 여럿 제공한다."
---
개인 프로젝트에 「실버」 글꼴을 사용하기로 했다.[^1] 무료 CJK 글꼴을 찾을 수는 있지만, 글꼴 하나로 CJK 문자를 커버할 수 있는지·섞어 썼을 때 잘 어울리는지·픽셀 아트 프로젝트에 적합한지 따위를 모두 고려하면, 사실 선택지 자체가 많지 않았다.[^2] 「실버」는 그런 요구에 부응할 뿐 아니라 게임과 관련된 특수문자를 여럿 제공하기 때문에, UI 구성에도 도움이 되리라 생각한다.[^3] 비트맵 스타일을 온전하게 살리려면 안티 앨리어싱이 적용되지 않도록 설정할 필요가 있어, 그 내용을 기록해두기로 한다.

[^1]: 「실버」 글꼴 배포처: <https://poppyworks.itch.io/silver>
[^2]: GNU 프로젝트 중 하나인 「[유니폰트 Unifont](https://unifoundry.com/unifont/index.html)」도 살펴봤지만, [BMP](/basic-multilingual-plane)를 거의 다 지원한다는 강점에도 불구하고 모양새가 마음에 들지 않았다.
[^3]: 「실버」 글꼴의 문자 지원 정보: <https://itch.io/t/488011/currently-supported-unicode-blocks>

# 유니티 에디터에서 사용하기

## `Silver.ttf` 설정

| 필드 | 값 |
|---|---|
| Font Size | `19`[^4][^5] |
| Rendering Mode | `Hinted Raster` |
| Character | `Dynamic` (기본값) |
| Ascent Calculation Mode | `Face ascender metric` (기본값) |
| Use Legacy Bounds | `false` (기본값) |
| Should Round Advanced Value | `true` (기본값) |
| Include Font Data | `true` (기본값) |

[^4]: 「실버」 글꼴의 크기 이슈에 대한 쓰레드: <https://itch.io/t/529134/solved-broken-text-in-unity>
[^5]: 게임 개발에 특화된 글꼴을 표방하는 만큼 배포 페이지에서 제공해야 할 정보라고 생각한다.

## Text Mesh Pro 글꼴 생성 옵션 설정

| 필드 | 값 |
|---|---|
| Source Font File | `Silver` (Font Asset) |
| Sampling Point Size | [Custom Size] `19`[^7] |
| Padding | `2` |
| Packing Method | `Fast` |
| Atlas Resolution | `2048×2048` |
| Character Set | [Custom Range] `0-65535` |
| Render Mode | `RASTER_HINTED` |
| Get Kerning Pairs | `false` (기본값) |

생성 결과: 질의 = 65536, 성공 = 13519, 실패 = 52017, 제외 = 0[^6]

[^6]: Text Mesh Pro용 「실버」 글꼴 생성 보고서: <https://raw.githubusercontent.com/oxmhpark/oxmhpark/refs/heads/main/attachments/TextMeshPro_GlyphReport-Silver.txt>
[^7]: 19배수 크기에서 가장 깔끔하게 보인다. 그보다 작은 크기에서는 획이 생략되는 등 가독성이 떨어지고, 그보다 큰 크기에서도 배수가 아니라면 가장자리가 깔끔하게 떨어지지 않는다. (렌더링 설정을 `Hinted Smooth`로 바꾸면 완화된다.)

## Text Mesh Pro 환경설정

| 필드 | 값 |
|---|---|
| Default Font Asset | `Silver` (TMP_Font Asset) |
| Default Font Size | `19` |
| [Text Auto Size Ratios] Min | `1` |
| [Text Auto Size Ratios] Max | `1` |