---
title: 키보드 매핑：상어60과 K9 Pro
slug: 키보드-매핑-상어60과-k9-pro
date: 2025-10-10 20:17:00 +0900
years:
  - 2025
categories:
  - 기기 관리
tags:
  - 포커 (레이아웃)
  - QMK (앱)
  - VIA (앱)
  - Zadig (앱)
excerpt: 현역인 K9 Pro와 백업용 상어60을 리매핑했다. 기존의 <kbd>Home</kbd>·<kbd>End</kbd>·<kbd>PgDn</kbd>·<kbd>PgUp</kbd> 입력 지원에 더해서, 3개의 <kbd>Fn</kbd> 키들-<kbd>SpaceFn</kbd>·<kbd>CapsLockFn</kbd>·<kbd>TabFn</kbd>-을 이용해서 <kbd>CapsLock</kbd>·<kbd>NumLock</kbd>·<kbd>ScrlLock</kbd>·<kbd>Print</kbd>·<kbd>F13</kbd>~<kbd>F24</kbd>·<kbd>M0</kbd>~<kbd>M15</kbd> 입력 지원을 추가했다.
---
키보드가 자리를 많이 차지하는 것을 싫어해서 포커 배열을 쓰기 시작한 지 십수년 쯤 됐다. 로우 프로파일 키보드인 `K9 Pro`에 정착한 지도 몇 해가 지났다. 최근 블로그 정비하면서 [더 빠른 문장부호 입력 방법](/단축키로-특수문자-입력하기)을 궁리하던 중, 키 매핑을 손봐서 <kbd>F13</kbd> ~ <kbd>F24</kbd> 키 코드를 단축키 지정에 활용하자는 아이디어가 떠올랐다. 

# 매핑 계획

## 기존 매핑

포커 배열 키보드는 우하단 특수키 4개 중 하나 이상을 <kbd>Fn</kbd> 키로 활용하는 경우가 많다. 그러나 표준 위치가 정해지지 않았다는 점에서 미완성으로 느껴졌고, 해당 영역 자체가 자주 누르기에 피곤했다. 그래서 활용 빈도는 낮지만 긴장 없이 누를 수 있는 <kbd>CapsLock</kbd>을 <kbd>Fn</kbd> 키로 전용해서 지금까지 사용했다. 여기에 더해, 우하단 특수키 4곳에 순서대로 <kbd>←</kbd> <kbd>↓</kbd> <kbd>↑</kbd> <kbd>→</kbd>를 매핑해서 키 조합 없이 방향을 입력할 수 있게 했다. 화살표들이 한 줄로 배치된 것은 타협이지만, `vi`의 <kbd>H</kbd> <kbd>J</kbd> <kbd>K</kbd> <kbd>L</kbd> 이동 시퀀스를 그대로 따른 것이므로 적응은 쉽다[^hjkl]. `Fn` 레이어에서는 관습에 따라 숫자 키 열에 <kbd>F1</kbd> ~ <kbd>F12</kbd>를, 커스텀 룰을 확장해서 우하단 특수키 4개에 순서대로 <kbd>Home</kbd> <kbd>PgDn</kbd> <kbd>PgUp</kbd> <kbd>End</kbd>를 배정했다.

[^hjkl]: 이 배열이 입력 빈도를 반영했다는 주장은 증명되지 않았지만, 코딩 환경에서는 타당하다고 본다.

| 레이어 | 위치                            | 기능                           |
|--------|---------------------------------|--------------------------------|
| 0      | <kbd>CapsLock</kbd>             | <kbd>Fn1</kbd>                 |
| 0      | <kbd>BR0</kbd>[^br0123]         | <kbd>←</kbd>                   |
| 0      | <kbd>BR1</kbd>                  | <kbd>↓</kbd>                   |
| 0      | <kbd>BR2</kbd>                  | <kbd>↑</kbd>                   |
| 0      | <kbd>BR3</kbd>                  | <kbd>→</kbd>                   |
| 0      | <kbd>Esc</kbd>                  | <kbd>Esc/~</kbd>               |
| 1      | <kbd>BR0</kbd>                  | <kbd>Home</kbd>                |
| 1      | <kbd>BR1</kbd>                  | <kbd>PgDn</kbd>                |
| 1      | <kbd>BR2</kbd>                  | <kbd>PgUp</kbd>                |
| 1      | <kbd>BR3</kbd>                  | <kbd>End</kbd>                 |
| 1      | <kbd>1/!</kbd> ~ <kbd>=/+</kbd> | <kbd>F1</kbd> ~ <kbd>F12</kbd> |
| 1      | <kbd>Esc</kbd>                  | <kbd>`/~</kbd>                 |
| 1      | <kbd>Bs</kbd>                   | <kbd>Del</kbd>                 |

[^br0123]: BR0~BR3은 우하단 특수키 네 개의 물리적 위치를 의미한다.

## 새 매핑

<kbd>SpaceFn</kbd>[^spacefn] 키 코드를 이용해 <kbd>Space</kbd> 키를 조건부 <kbd>Fn1</kbd> 키로 사용하고, 기존 <kbd>CapsLock</kbd> 위치는 <kbd>Fn2</kbd>로 배정했다. 추가된 `Fn2` 레이어에서는 <kbd>F11</kbd> ~ <kbd>F24</kbd> 입력을 받는다. 이 방식은 <kbd>Space</kbd> 키를 홀드해서 공백을 연속으로 입력할 수 없는 단점이 있다. 그러나 기능을 희생하지 않고 추가 레이어에 접근할 수 있으며 가장 사용 빈도가 높고 편안한 키를 중심으로 조작할 수 있다는 장점이 있다.

| 레이어 | 위치                            | 기능                            |
|--------|---------------------------------|---------------------------------|
| 0      | <kbd>Space</kbd>                | <kbd>SpaceFn1</kbd>             |
| 0      | <kbd>CapsLock</kbd>             | <kbd>Fn2</kbd>                  |
| 0      | <kbd>BR0</kbd>                  | <kbd>←</kbd>                    |
| 0      | <kbd>BR1</kbd>                  | <kbd>↓</kbd>                    |
| 0      | <kbd>BR2</kbd>                  | <kbd>↑</kbd>                    |
| 0      | <kbd>BR3</kbd>                  | <kbd>→</kbd>                    |
| 0      | <kbd>Esc</kbd>                  | <kbd>Esc/~</kbd>                |
| 1      | <kbd>BR0</kbd>                  | <kbd>Home</kbd>                 |
| 1      | <kbd>BR1</kbd>                  | <kbd>PgDn</kbd>                 |
| 1      | <kbd>BR2</kbd>                  | <kbd>PgUp</kbd>                 |
| 1      | <kbd>BR3</kbd>                  | <kbd>End</kbd>                  |
| 1      | <kbd>1/!</kbd> ~ <kbd>=/+</kbd> | <kbd>F1</kbd> ~ <kbd>F12</kbd>  |
| 1      | <kbd>Esc</kbd>                  | <kbd>`/~</kbd>                  |
| 1      | <kbd>Bs</kbd>                   | <kbd>Del</kbd>                  |
| 2      | <kbd>1/!</kbd> ~ <kbd>=/+</kbd> | <kbd>F11</kbd> ~ <kbd>F22</kbd> |
| 2      | <kbd>[/{</kbd> ~ <kbd>]/}</kbd> | <kbd>F23</kbd> ~ <kbd>F24</kbd> |
| 2      | <kbd>BR0</kbd>                  | <kbd>CapsLock</kbd>             |
| 2      | <kbd>BR1</kbd>                  | <kbd>NumLock</kbd>              |
| 2      | <kbd>BR2</kbd>                  | <kbd>ScrlLock</kbd>             |
| 2      | <kbd>BR3</kbd>                  | <kbd>Print</kbd>                |

[^spacefn]: <kbd>Space</kbd> 키를 홀드하는 동안에는 <kbd>Fn1</kbd> 키로, 릴리즈하는 순간에는 <kbd>Space</kbd> 키로 동작한다.

## 매크로 예비

`K9 Pro`가 `VIA` 앱을 지원한다는 점을 이용해서 미리 매크로 레이어를 추가했다.

| 레이어 | 위치                            | 기능                            |
|--------|---------------------------------|---------------------------------|
| 1      | <kbd>Tab</kbd>                  | <kbd>Fn3</kbd>                  |
| 2      | <kbd>Tab</kbd>                  | <kbd>Fn3</kbd>                  |
| 3      | <kbd>Esc</kbd>                  | <kbd>M0</kbd>                   |
| 3      | <kbd>1/!</kbd> ~ <kbd>=/+</kbd> | <kbd>M1</kbd> ~ <kbd>M12</kbd>  |
| 3      | <kbd>[/{</kbd> ~ <kbd>]/}</kbd> | <kbd>M13</kbd> ~ <kbd>M14</kbd> |
| 3      | <kbd>Bs</kbd>                   | <kbd>M15</kbd>                  |

# 레이아웃 업데이트

## 상어60

구입 당시 널리 쓰이던 `DZ60` 보드[^dz60-controller][^dz60-dfu-hotkey]가 설치된 키보드. 해당 보드는 `VIA` 앱을 지원하지 않으므로[^dz60-via-support] `QMK Configurator`로 매핑 프로필과 펌웨어를 마련하고 `QMK Toolkit`으로 플래싱했다. 첫 시도는 드라이버 불일치 이슈[^dz60-driver-error]로 실패했지만, `Zadig` 앱으로 드라이버를 강제로 변경[^dz60-driver-fix]하고 플래싱에 성공했다.

[^dz60-via-support]: 본 작업에서는 장치를 인식시키는 방법이 있는지 조사하지 않았다.
[^dz60-controller]: `ATmega32U4` 컨트롤러를 사용한다.
[^dz60-dfu-hotkey]: `DFU` 모드 진입 방법은 USB 케이블 연결 시 <kbd>Esc</kbd> 키를 홀드하는 것이다.
[^dz60-driver-error]: `Atmel DFU device has libusb0 driver assigned but should be WinUSB. Flashing may not succeed.`
[^dz60-driver-fix]: `DFU` 모드에서 드라이버를 `libusb0` → `winusb`으로 변경했다.

## K9 Pro

이 키보드는 외장에 노출된 OS 선택(Win/Mac) 스위치로 기본 레이어를 지정(0/1)하는 기능이 있어 확장 레이어 인덱스를 1씩 밀어야 했다. `VIA` 앱은 매핑하는 즉시 하드웨어에 반영되기 때문에 작업은 단순했다.

# 결과 보고

1. 키 조합 없이 <kbd>←</kbd>, <kbd>↓</kbd>, <kbd>↑</kbd>, <kbd>→</kbd> 키 코드를 입력할 수 있다.
2. <kbd>Space</kbd> 키 조합으로 <kbd>F1</kbd> ~ <kbd>F12</kbd>, <kbd>Home</kbd>, <kbd>End</kbd>, <kbd>PgDn</kbd>, <kbd>PgUp</kbd> 키 코드를 입력할 수 있다.
3. <kbd>CapsLock</kbd> 키 조합으로 <kbd>F11</kbd> ~ <kbd>F24</kbd>, <kbd>CapsLock</kbd>, <kbd>NumLock</kbd>, <kbd>ScrlLock</kbd>, <kbd>Print</kbd> 키 코드를 입력할 수 있다.
4. (K9 Pro 한정) <kbd>Space</kbd> + <kbd>Tab</kbd> 또는 <kbd>CapsLock</kbd> + <kbd>Tab</kbd> 키 조합으로 <kbd>M0</kbd> ~ <kbd>M15</kbd> 키 코드를 입력할 수 있다.