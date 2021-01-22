---
description: '詳細: `chrono` リテラル'
title: chrono リテラル
f1_keywords:
- chrono/std::literals::chrono_literals
- std::literals::chrono_literals
- chrono_literals
ms.date: 01/15/2021
ms.openlocfilehash: 84540d111b33738c8bb1bcb4b43966e1c50682c0
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667552"
---
# <a name="chrono-literals"></a>`chrono` リテラル

(C++ 14)ヘッダーには、 `<chrono>` 時間、分、秒、ミリ秒、マイクロ秒、ナノ秒を表す12個の [ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md) が定義されています。 各ユーザー定義リテラルには、整数と浮動小数点数のオーバーロードがあります。 リテラルはインライン名前空間で定義され `literals::chrono_literals` 、 `std::chrono` がスコープ内にあるときに自動的にスコープに取り込まれます。

## <a name="syntax"></a>構文

```cpp
inline namespace literals {
  inline namespace chrono_literals {
    // return integral hours
    constexpr chrono::hours operator"" h(unsigned long long Val);

    // return floating-point hours
    constexpr chrono::duration<double, ratio<3600>> operator"" h(long double Val);

    // return integral minutes
    constexpr chrono::minutes(operator"" min)(unsigned long long Val);

    // return floating-point minutes
    constexpr chrono::duration<double, ratio<60>>(operator"" min)(long double Val);

    // return integral seconds
    constexpr chrono::seconds operator"" s(unsigned long long Val);

    // return floating-point seconds
    constexpr chrono::duration<double> operator"" s(long double Val);

    // return integral milliseconds
    constexpr chrono::milliseconds operator"" ms(unsigned long long Val);

    // return floating-point milliseconds
    constexpr chrono::duration<double, milli> operator"" ms(long double Val);

    // return integral microseconds
    constexpr chrono::microseconds operator"" us(unsigned long long Val);

    // return floating-point microseconds
    inline constexpr chrono::duration<double, micro> operator"" us(long double Val);

    // return integral nanoseconds
    inline constexpr chrono::nanoseconds operator"" ns(unsigned long long Val);

    // return floating-point nanoseconds
    constexpr chrono::duration<double, nano> operator"" ns(long double Val);

  } // inline namespace chrono_literals
} // inline namespace literals
```

## <a name="return-value"></a>戻り値

引数を受け取るリテラルは、 **`long long`** 値または対応する型を返します。 浮動小数点引数を受け取るリテラルは、を返し [`duration`](../standard-library/duration-class.md) ます。

## <a name="example"></a>例

次の例は、リテラルの使用方法を示して `chrono` います。

```cpp
constexpr auto day = 24h;
constexpr auto week = 24h* 7;
constexpr auto my_duration_unit = 108ms;
```
