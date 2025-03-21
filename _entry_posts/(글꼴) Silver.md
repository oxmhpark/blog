---
published: true
title: "Silver"
subtitle: "CJK 지원 비트맵 스타일 글꼴"
slug: "silver-글꼴"
date: 2025-02-21 00:00:00 +0900
year: 2025
categories:
  - 개발노트
  - 프로젝트 용사전진
tags:
  - 게임 개발
  - 픽셀 아트
  - 글꼴
  - 소개
  - 모바일 방치형 게임 만들기
excerpt: "《Silver》는 CJK 문자표를 상당 부분 지원하는 비트맵 스타일의 글꼴이다. 다국어를 지원하는 픽셀 아트 풍의 앱 개발에 잘 어울리며, 게임과 관련된 특수문자를 여럿 제공해서 레트로 게임 개발에 좀 더 유용하다. 이 문서에서는 유니티 엔진에서 Pixel Perfect 프로젝트를 개발하는 경우의 적용 방법을 취급한다."
---

《Silver》[^1]는 CJK 문자표를 상당 부분 지원하는 비트맵 스타일의 글꼴이다.[^2] 다국어를 지원하는 픽셀 아트 풍의 앱 개발에 잘 어울리며, 게임과 관련된 특수문자를 여럿 제공해서 레트로 게임 개발에 좀 더 유용하다. 이 문서에서는 유니티 엔진에서 Pixel Perfect 프로젝트를 개발하는 경우의 적용 방법을 취급한다.

# 글꼴 파일 임포트: Silver.ttf
- Font Size: 19[^3][^4]
- Rendering Mode: Hinted Raster
- Character: Dynamic (기본값)
- Ascent Calculation Mode: Face ascender metric (기본값)
- Use Legacy Bounds: false (기본값)
- Should Round Advanced Value: true (기본값)
- Include Font Data: true (기본값)

# Text Mesh Pro 글꼴로 변환: Silver.asset
- Source Font File: Silver
- Sampling Point Size: [Custom Size] 19
- Padding: 2
- Packing Method: Fast
- Atlas Resolution: 2048×2048
- Character Set: [Custom Range] 0-65535
- Render Mode: RASTER_HINTED
- Get Kerning Pairs: false (기본값)
- 생성 결과: 질의 = 65536, 성공 = 13519, 실패 = 52017, 제외 = 0[^5]

# Text Mesh Pro 설정 에셋에서 기본 글꼴로 지정
- Default Font Asset: Silver (TMP_Font Asset)
- Default Font Size: 19
- Text Auto Size Ratios: Min = 1, Max = 1

# 주의점
- 19의 배수 크기에서 가장 깔끔하게 보인다.
- 19보다 작은 크기에서는 가독성이 떨어진다.
- 19보다 큰 크기에서도 배수가 아니라면 가장자리가 뭉개진다.[^6]

[^1]: 배포처: <https://poppyworks.itch.io/silver>
[^2]: 표: <https://itch.io/t/488011/currently-supported-unicode-blocks>
[^3]: 출처: <https://itch.io/t/529134/solved-broken-text-in-unity>
[^4]: 게임 개발에 특화된 글꼴을 표방하는 만큼 배포 페이지에서 제공해야 할 정보라고 생각한다.
[^5]: 보고서: <https://raw.githubusercontent.com/oxmhpark/oxmhpark/refs/heads/main/attachments/TextMeshPro_GlyphReport-Silver.txt>
[^6]: 글꼴 에셋의 렌더링 설정을 Hinted Smooth로 바꾸면 완화된다.