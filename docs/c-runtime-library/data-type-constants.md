---
description: '詳細情報: データ型の定数'
title: データ型定数
ms.date: 06/25/2018
f1_keywords:
- FLT_MIN
- SHRT_MAX
- CHAR_MIN
- MB_LEN_MAX
- DBL_EPSILON
- SHRT_MIN
- _FLT_RADIX
- FLT_DIG
- FLT_MAX_10_EXP
- FLT_MANT_DIG
- DBL_MAX_EXP
- SCHAR_MIN
- SCHAR_MAX
- DBL_MIN
- FLT_MIN_10_EXP
- _DBL_ROUNDS
- USHRT_MAX
- FLT_MAX_EXP
- LONG_MAX
- DBL_MAX
- DBL_DIG
- FLT_MIN_EXP
- INT_MIN
- DBL_MIN_10_EXP
- CHAR_BIT
- INT_MAX
- ULONG_MAX
- DBL_MIN_EXP
- LONG_MIN
- _FLT_ROUNDS
- DBL_MANT_DIG
- _DBL_RADIX
- CHAR_MAX
- FLT_MAX
- DBL_MAX_10_EXP
- UCHAR_MAX
- FLT_EPSILON
- UINT_MAX
- LLONG_MIN
- LLONG_MAX
- ULLONG_MAX
- _I8_MIN
- _I8_MAX
- _UI8_MAX
- _I16_MIN
- _I16_MAX
- _UI16_MAX
- _I32_MIN
- _I32_MAX
- _UI32_MAX
- _I64_MIN
- _I64_MAX
- _UI64_MAX
- _I128_MIN
- _I128_MAX
- _UI128_MAX
- SIZE_MAX
- RSIZE_MAX
- LDBL_DIG
- LDBL_EPSILON
- LDBL_HAS_SUBNORM
- LDBL_MANT_DIG
- LDBL_MAX
- LDBL_MAX_10_EXP
- LDBL_MAX_EXP
- LDBL_MIN
- LDBL_MIN_10_EXP
- LDBL_MIN_EXP
- _LDBL_RADIX
- LDBL_TRUE_MIN
- DECIMAL_DIG
helpviewer_keywords:
- DBL_MAX_EXP constant
- _DBL_RADIX constant
- FLT_MIN_EXP constant
- DBL_EPSILON constant
- INT_MIN constant
- FLT_EPSILON constant
- DBL_MANT_DIG constant
- _FLT_RADIX constant
- DBL_MIN constant
- USHRT_MAX constant
- FLT_MAX_10_EXP constant
- _FLT_ROUNDS constant
- data type constants [C++]
- _DBL_ROUNDS constant
- CHAR_MAX constant
- FLT_MAX_EXP constant
- FLT_MIN constant
- CHAR_MIN constant
- FLT_MIN_10_EXP constant
- DBL_MIN_EXP constant
- SCHAR_MAX constant
- FLT_RADIX constant
- CHAR_BIT constant
- UCHAR_MAX constant
- DBL_RADIX constant
- FLT_ROUNDS constant
- LONG_MIN constant
- SHRT_MAX constant
- LONG_MAX constant
- DBL_MAX_10_EXP constant
- DBL_MIN_10_EXP constant
- INT_MAX constant
- constants [C++], data type
- ULONG_MAX constant
- FLT_DIG constant
- MB_LEN_MAX constant
- DBL_DIG constant
- SHRT_MIN constant
- DBL_MAX constant
- DBL_ROUNDS constant
- FLT_MAX constant
- UINT_MAX constant
- FLT_MANT_DIG constant
- SCHAR_MIN constant
- LLONG_MIN constant
- LLONG_MAX constant
- ULLONG_MAX constant
- _I8_MIN constant
- _I8_MAX constant
- _UI8_MAX constant
- _I16_MIN constant
- _I16_MAX constant
- _UI16_MAX constant
- _I32_MIN constant
- _I32_MAX constant
- _UI32_MAX constant
- _I64_MIN constant
- _I64_MAX constant
- _UI64_MAX constant
- _I128_MIN constant
- _I128_MAX constant
- _UI128_MAX constant
- SIZE_MAX constant
- RSIZE_MAX constant
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
ms.openlocfilehash: eb1c16cb730ea40a60a5929867fa8a36b17190ec
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258838"
---
# <a name="data-type-constants"></a>データ型定数

データ型定数は、整数データ型と浮動小数点データ型に許可される実装依存の値範囲です。

## <a name="integral-type-constants"></a>整数型の定数

これらの定数は、整数データ型の範囲を示します。 これらの定数を使用するには、ソース ファイルに limits.h ヘッダーをインクルードします。

```C
#include <limits.h>
```

> [!NOTE]
> [`/J`](../build/reference/j-default-char-type-is-unsigned.md)コンパイラオプションは、既定の **`char`** 型をからに変更し **`signed char`** **`unsigned char`** ます。

|定数|値|説明|
|--------------|-----------|-------------|
|**CHAR_BIT**|8|のビット数 **`char`**|
|**SCHAR_MIN**|(-128)|最小 **`signed char`** 値|
|**SCHAR_MAX**|127|最大 **`signed char`** 値|
|**UCHAR_MAX**|255 (0xff)|最大 **`unsigned char`** 値|
|**CHAR_MIN**|(-128)(オプションが **`/J`** 使用された場合は 0)|最小 **`char`** 値|
|**CHAR_MAX**|127 (オプションが **`/J`** 使用されている場合は 255)|最大 **`char`** 値|
|**MB_LEN_MAX**|5|マルチバイトの最大バイト数 **`char`**|
|**SHRT_MIN**|-32768|最小 **`signed short`** 値|
|**SHRT_MAX**|32767|最大 **`signed short`** 値|
|**USHRT_MAX**|65535 (0xffff)|最大 **`unsigned short`** 値|
|**INT_MIN**|(-2147483647 - 1)|最小 **`signed int`** 値|
|**INT_MAX**|2147483647|最大 **`signed int`** 値|
|**UINT_MAX**|4294967295 (0xffffffff)|最大 **`unsigned int`** 値|
|**LONG_MIN**|(-2147483647L - 1)|最小 **`signed long`** 値|
|**LONG_MAX**|2147483647L|最大 **`signed long`** 値|
|**ULONG_MAX**|4294967295UL (0xfffffffful)|最大 **`unsigned long`** 値|
|**LLONG_MIN**|(-9223372036854775807LL - 1)|最小 **`signed long long`** 値または **`__int64`** 値|
|**LLONG_MAX**|9223372036854775807LL|最大 **`signed long long`** 値または **`__int64`** 値|
|**ULLONG_MAX**|0xffffffffffffffffull|最大 **`unsigned long long`** 値|
|**_I8_MIN**|(-127i8 - 1)|最小符号付き 8 ビット値|
|**_I8_MAX**|127i8|最大符号付き 8 ビット値|
|**_UI8_MAX**|0xffui8|最大符号なし 8 ビット値|
|**_I16_MIN**|(-32767i16 - 1)|最小符号付き 16 ビット値|
|**_I16_MAX**|32767i16|最大符号付き 16 ビット値|
|**_UI16_MAX**|0xffffui16|最大符号なし 16 ビット値|
|**_I32_MIN**|(-2147483647i32 - 1)|最小符号付き 32 ビット値|
|**_I32_MAX**|2147483647i32|最大符号付き 32 ビット値|
|**_UI32_MAX**|0xffffffffui32|最大符号なし 32 ビット値|
|**_I64_MIN**|(-9223372036854775807 - 1)|最小符号付き 64 ビット値|
|**_I64_MAX**|9223372036854775807|最大符号付き 64 ビット値|
|**_UI64_MAX**|0xffffffffffffffffui64|最大符号なし 64 ビット値|
|**_I128_MIN**|(-170141183460469231731687303715884105727i128 - 1)|最小符号付き 128 ビット値|
|**_I128_MAX**|170141183460469231731687303715884105727i128|最大符号付き 128 ビット値|
|**_UI128_MAX**|0xffffffffffffffffffffffffffffffffui128|最大符号なし 128 ビット値|
|**SIZE_MAX**|**_WIN64** が定義されている場合は **_UI64_MAX** と同じ、それ以外の場合は **UINT_MAX**|最大ネイティブ整数サイズ|
|**RSIZE_MAX**|(**SIZE_MAX** >> 1) と同じ|セキュリティで保護された最大ライブラリ整数サイズ|

## <a name="floating-point-type-constants"></a>浮動小数点型定数

次の定数は、、、およびデータ型の範囲とその他の特性を指定し **`long double`** **`double`** **`float`** ます。 これらの定数を使用するには、ソース ファイルに float.h ヘッダーをインクルードします。

```C
#include <float.h>
```

|定数|値|説明|
|--------------|-----------|-----------------|
|**DBL_DECIMAL_DIG**|17|丸め精度の有効桁数|
|**DBL_DIG**|15|有効桁数|
|**DBL_EPSILON**|2.2204460492503131e-016|1.0 + **DBL_EPSILON** != 1.0 のように最小|
|**DBL_HAS_SUBNORM**|1|入力は正常未満 (非正規) 数をサポートします|
|**DBL_MANT_DIG**|53|有効桁 (仮数) のビット数|
|**DBL_MAX**|1.7976931348623158e+308|最大値|
|**DBL_MAX_10_EXP**|308|最大 10 進指数|
|**DBL_MAX_EXP**|1024|最大 2 進指数|
|**DBL_MIN**|2.2250738585072014e-308|正規化された正の最小数|
|**DBL_MIN_10_EXP**|(-307)|最小 10 進指数|
|**DBL_MIN_EXP**|(-1021)|最小 2 進指数|
|**_DBL_RADIX**|2|指数の基数|
|**DBL_TRUE_MIN**|4.9406564584124654e-324|正常未満の正の最小数|
|**FLT_DECIMAL_DIG**|9|丸め精度の有効桁数|
|**FLT_DIG**|6|有効桁数|
|**FLT_EPSILON**|1.192092896e-07F|1.0 + **FLT_EPSILON** != 1.0 のように最小|
|**FLT_HAS_SUBNORM**|1|入力は正常未満 (非正規) 数をサポートします|
|**FLT_MANT_DIG**|24|有効桁 (仮数) のビット数|
|**FLT_MAX**|3.402823466e+38F|最大値|
|**FLT_MAX_10_EXP**|38|最大 10 進指数|
|**FLT_MAX_EXP**|128|最大 2 進指数|
|**FLT_MIN**|1.175494351e-38F|正規化された正の最小数|
|**FLT_MIN_10_EXP**|(-37)|最小 10 進指数|
|**FLT_MIN_EXP**|(-125)|最小 2 進指数|
|**FLT_RADIX**|2|指数の基数|
|**FLT_TRUE_MIN**|1.401298464e-45F|正常未満の正の最小数|
|**LDBL_DIG**|15|有効桁数|
|**LDBL_EPSILON**|2.2204460492503131e-016|1.0 + **LDBL_EPSILON** != 1.0 のように最小|
|**LDBL_HAS_SUBNORM**|1|入力は正常未満 (非正規) 数をサポートします|
|**LDBL_MANT_DIG**|53|有効桁 (仮数) のビット数|
|**LDBL_MAX**|1.7976931348623158e+308|最大値|
|**LDBL_MAX_10_EXP**|308|最大 10 進指数|
|**LDBL_MAX_EXP**|1024|最大 2 進指数|
|**LDBL_MIN**|2.2250738585072014e-308|正規化された正の最小数|
|**LDBL_MIN_10_EXP**|(-307)|最小 10 進指数|
|**LDBL_MIN_EXP**|(-1021)|最小 2 進指数|
|**_LDBL_RADIX**|2|指数の基数|
|**LDBL_TRUE_MIN**|4.9406564584124654e-324|正常未満の正の最小数|
|**DECIMAL_DIG**|**DBL_DECIMAL_DIG** と同じ|既定 (倍精度) の丸め精度の有効桁数|

## <a name="see-also"></a>関連項目

[グローバル定数](../c-runtime-library/global-constants.md)
