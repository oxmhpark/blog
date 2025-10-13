---
title: C＃：주요 메모
slug: c＃-주요-메모
abbr: C＃：Cheatsheet
date: 2025-03-30 13:19:47 +0900
years:
  - 2025
categories:
  - 개발일지
tags:
  - 유니티 엔진
  - 고도 엔진
  - C샾
excerpt: 정수 / 실수 / 플래그 / 문자 / 날짜·시간 / 기타 타입 / 논리 AND 연산자 <code>&amp;</code> / 논리 OR 연산자 <code>|</code> / 논리 베타적 OR 연산자 <code>^</code> / 비트 보수 연산자 <code>~</code> / 논리 이동 연산자 <code>&lt;&lt;</code>, <code>&gt;&gt;</code> / 논리 및 비트 연산자 우선순위
---
# 주요 타입

## 정수

| 타입 이름 | 최소값 | 최대값 | 특징 |
|---|---|---|---|
| [`byte`][ref-byte] | `0` | `255` | 부호 없는 8비트 정수 |
| [`sbyte`][ref-sbyte] | `-128` | `127` | 부호 있는 8비트 정수 |
| [`short`][ref-short] | `-32768` | `32767` | 부호 있는 16비트 정수 |
| [`ushort`][ref-ushort] | `0` | `65535` | 부호 없는 16비트 정수 |
| [`int`][ref-int] | `-2147483648` | `2147483647` | 부호 있는 32비트 정수 |
| [`uint`][ref-uint] | `0` | `4294967295` | 부호 없는 32비트 정수 |
| [`long`][ref-long] | `-9223372036854775808` | `9223372036854775807` | 부호 있는 64비트 정수 |
| [`ulong`][ref-ulong] | `0` | `18446744073709551615` | 부호 없는 64비트 정수 |
| [`BigInteger`][ref-biginteger] | - | - | 최소·최대값이 없는 큰 정수<br />`System.Numerics` 이름공간에 정의됨. |

[ref-byte]: https://learn.microsoft.com/en-us/dotnet/api/system.byte
[ref-sbyte]: https://learn.microsoft.com/en-us/dotnet/api/system.sbyte
[ref-short]: https://learn.microsoft.com/en-us/dotnet/api/system.int16
[ref-ushort]: https://learn.microsoft.com/en-us/dotnet/api/system.uint16
[ref-int]: https://learn.microsoft.com/en-us/dotnet/api/system.int32
[ref-uint]: https://learn.microsoft.com/en-us/dotnet/api/system.uint32
[ref-long]: https://learn.microsoft.com/en-us/dotnet/api/system.int64
[ref-ulong]: https://learn.microsoft.com/en-us/dotnet/api/system.uint64
[ref-biginteger]: https://learn.microsoft.com/en-us/dotnet/api/system.numerics.biginteger

## 실수

| 타입 이름 | 최소값 | 최대값 | 특징 |
|---|---|---|---|
| [`float`][ref-float] | `-3.4028235E+38` | `3.4028235E+38` | |
| [`double`][ref-double] | `-1.7976931348623157E+308` | `1.7976931348623157E+308` | |
| [`decimal`][ref-decimal] | `-79228162514264337593543950335` | `79228162514264337593543950335` | |

[ref-float]: https://learn.microsoft.com/en-us/dotnet/api/system.single
[ref-double]: https://learn.microsoft.com/en-us/dotnet/api/system.double
[ref-decimal]: https://learn.microsoft.com/en-us/dotnet/api/system.decimal

## 플래그

| 타입 이름 | 최소값 | 최대값 | 특징 |
|---|---|---|---|
| [`bool`][ref-bool] | `false` | `true` | 논리값 |
| [`enum`][ref-enum] | - | - | 구체적인 타입으로 상속받아야 한다. |

[ref-bool]: https://learn.microsoft.com/en-us/dotnet/api/system.boolean
[ref-enum]: https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/builtin-types/enum

## 문자

| 타입 이름 | 값 | 특징 |
|---|---|---|
| [`char`][ref-char] | 문자 | 작은 따옴표로 감싼다. |
| [`string`][ref-string] | 문자열 | 큰 따옴표로 감싼다. |

[ref-char]: https://learn.microsoft.com/en-us/dotnet/api/system.char
[ref-string]: https://learn.microsoft.com/en-us/dotnet/api/system.string

## 날짜·시간

| 타입 이름 | 특징 |
|---|---|
| [`DateTime`][ref-DateTime] |  |
| [`TimeSpan`][ref-TimeSpan] |  |
| [`DateOnly`][ref-dateonly] | 날짜만 표현 (C# 10 이상) |
| [`TimeOnly`][ref-timeonly] | 시간만 표현 (C# 10 이상) |

[ref-datetime]: https://learn.microsoft.com/en-us/dotnet/api/system.datetime
[ref-timespan]: https://learn.microsoft.com/en-us/dotnet/api/system.timespan
[ref-dateonly]: https://learn.microsoft.com/en-us/dotnet/api/system.dateonly
[ref-timeonly]: https://learn.microsoft.com/en-us/dotnet/api/system.timeonly

## 기타

| 타입 이름 | 특징 |
|---|---|
| [`Guid`][ref-guid] | 전역적 고유 식별자 |
| [`nint`][ref-nint] | 플랫폼 종속 정수형 (C# 9 이상) |
| [`nuint`][ref-nuint] | 부호 없는 플랫폼 종속 정수형 (C# 9 이상) |

[ref-guid]: https://learn.microsoft.com/en-us/dotnet/api/system.guid
[ref-nint]: https://learn.microsoft.com/en-us/dotnet/api/system.nint
[ref-nuint]: https://learn.microsoft.com/en-us/dotnet/api/system.nuint

# 비트 연산자

|| 표현 | Binary | Decimal |
|---|---|---|---|
| 예제 변수 | `x` | 000110 | 6 |
| 예제 변수 | `y` | 001100 | 12 |
| [논리 AND 연산자 `&`][ref-and] | `x & y` | 000100 | 4 |
| [논리 OR 연산자 `\|`][ref-or] | `x \| y` | 001110 | 14 |
| [논리 베타적 OR 연산자 `^`][ref-xor] | `x ^ y` | 001010 | 10 |
| [비트 보수 연산자 `~`][ref-not] | `~x` | 111001 | 9 |
| [비트 이동 연산자 `<<`][ref-이동-left] | `x << 1` | 001100 | 12 |
| | `x << 2` | 011000 | 24 |
| [비트 이동 연산자 `>>`][ref-이동-right] | `x >> 1` | 000011 | 3 |
|  | `x >> 2` | 000001 | 1 |

[ref-and]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#logical-and-operator-
[ref-or]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#logical-or-operator-
[ref-xor]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#logical-exclusive-or-operator-
[ref-not]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#bitwise-complement-operator-
[ref-이동-left]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#left-이동-operator-
[ref-이동-right]: https://learn.microsoft.com/ko-kr/dotnet/csharp/language-reference/operators/bitwise-and-이동-operators#right-이동-operator-

## 논리 및 비트 연산자 우선순위

1. 비트 보수 연산자 `~`
2. 시프트 연산자 `<<`, `>>`, `>>>`
3. 논리 AND 연산자 `&`
4. 논리 배타적 OR 연산자 `^`
5. 논리 OR 연산자 `|`
