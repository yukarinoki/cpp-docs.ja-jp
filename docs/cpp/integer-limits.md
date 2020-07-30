---
title: 整数の制限
ms.date: 01/29/2018
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
ms.openlocfilehash: a113dd687e6f135af950f461e024b9fd9feaf1b5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213386"
---
# <a name="integer-limits"></a>整数の制限

**Microsoft 固有の仕様**

次の表に、整数型の制限を示します。 これらの制限のプリプロセッサマクロは、標準ヘッダーファイルをインクルードするときにも定義され \<climits> ます。

## <a name="limits-on-integer-constants"></a>整数定数の制限

| 定数 | 説明 | [値] |
|--|--|--|
| `CHAR_BIT` | ビット フィールドではない最小変数のビット数。 | 8 |
| `SCHAR_MIN` | 型の変数の最小値 **`signed char`** 。 | -128 |
| `SCHAR_MAX` | 型の変数の最大値 **`signed char`** 。 | 127 |
| `UCHAR_MAX` | 型の変数の最大値 **`unsigned char`** 。 | 255 (0xff) |
| `CHAR_MIN` | 型の変数の最小値 **`char`** 。 | -128;0の場合、 **`/J`** オプションが使用されます。 |
| `CHAR_MAX` | 型の変数の最大値 **`char`** 。 | 127;255 **`/J`** オプションが使用されている場合 |
| `MB_LEN_MAX` | 多文字定数の最大バイト数。 | 5 |
| `SHRT_MIN` | 型の変数の最小値 **`short`** 。 | -32768 |
| `SHRT_MAX` | 型の変数の最大値 **`short`** 。 | 32767 |
| `USHRT_MAX` | 型の変数の最大値 **`unsigned short`** 。 | 65535 (0xffff) |
| `INT_MIN` | 型の変数の最小値 **`int`** 。 | -2147483648 |
| `INT_MAX` | 型の変数の最大値 **`int`** 。 | 2147483647 |
| `UINT_MAX` | 型の変数の最大値 **`unsigned int`** 。 | 4294967295 (0xffffffff) |
| `LONG_MIN` | 型の変数の最小値 **`long`** 。 | -2147483648 |
| `LONG_MAX` | 型の変数の最大値 **`long`** 。 | 2147483647 |
| `ULONG_MAX` | 型の変数の最大値 **`unsigned long`** 。 | 4294967295 (0xffffffff) |
| `LLONG_MIN` | 型の変数の最小値**`long long`** | -9223372036854775808 |
| `LLONG_MAX` | 型の変数の最大値**`long long`** | 9223372036854775807 |
| `ULLONG_MAX` | 型の変数の最大値**`unsigned long long`** | 18446744073709551615 (0xffffffffffffffff) |

値が最大の整数表現を超えると、Microsoft コンパイラでエラーが生成されます。

## <a name="see-also"></a>関連項目

[浮動小数点の制限](../cpp/floating-limits.md)
