---
title: データ型定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
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
dev_langs:
- C++
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
ms.assetid: c0f1c405-0465-41d5-b5ff-e81cdb6f1622
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: cf9a64b81ae90c517e9cd15e796dfb1333c7b08c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392147"
---
# <a name="data-type-constants"></a>データ型定数
データ型定数は、整数データ型に許可される実装依存の値範囲です。 下の一覧の定数は整数データ型の範囲を与えるものであり、LIMITS.H で定義されています。  
  
> [!NOTE]
>  /J コンパイラ オプションは、既定値を `char` から `unsigned` に変更します。  
  
|定数|[値]|説明|  
|--------------|-----------|-------------|  
|**SCHAR_MAX**|127|最大符号付き `char` 値|  
|**SCHAR_MIN**|-128|最小符号付き `char` 値|  
|**UCHAR_MAX**|255 (0xff)|最大 `unsigned char` 値|  
|**CHAR_BIT**|8|`char` のビット数|  
|**USHRT_MAX**|65535 (0xffff)|最大**符号なしの short** 値|  
|**SHRT_MAX**|32767|最大 (符号付き) **short**値|  
|**SHRT_MIN**|-32768|最小 (符号付き) **short**値|  
|**UINT_MAX**|4294967295 (0xffffffff)|最大 `unsigned int` 値|  
|**ULONG_MAX**|4294967295 (0xffffffff)|最大 `unsigned long` 値|  
|**INT_MAX**|2147483647|最大 (符号付き) `int` 値|  
|**INT_MIN**|-2147483647-1|最小 (符号付き) `int` 値|  
|**LONG_MAX**|2147483647|最大 (符号付き) **long** 値|  
|**LONG_MIN**|-2147483647-1|最小 (符号付き) **long** 値|  
|**CHAR_MAX**|127 (/J オプションが使用される場合は 255)|最大 `char` 値|  
|**CHAR_MIN**|-128 (/J オプションが使用される場合は 0)|最小 `char` 値|  
|**MB_LEN_MAX**|2|マルチバイト `char` の最大バイト数|  
|**_I64_MAX**|9223372036854775807|最大 (符号付き) __**int64** 値|  
|**_I64_MIN**|-9223372036854775807-1|最小 (符号付き) __**int64** 値|  
|**_UI64_MAX**|0xffffffffffffffff|最大 (符号なし) __**int64** 値|  
  
 次の定数は **double** 型と **float** 型の範囲とその他の特徴を与え、FLOAT.H で定義されます。  
  
|定数|[値]|説明|  
|--------------|-----------|-----------------|  
|**DBL_DIG**|16|有効桁数|  
|**DBL_EPSILON**|2.2204460492503131e-016|1.0+**DBL_EPSILON** !=1.0 のように最小|  
|**DBL_MANT_DIG**|53|仮数部のビット数|  
|**DBL_MAX**|1.7976931348623158e+308|最大値|  
|**DBL_MAX_10_EXP**|308|最大 10 進指数|  
|**DBL_MAX_EXP**|1024|最大 2 進指数|  
|**DBL_MIN**|2.2250738585072014e-308|正の最小数|  
|**DBL_MIN_10_EXP**|(-307)|最小 10 進指数|  
|**DBL_MIN_EXP**|(-1021)|最小 2 進指数|  
|**_DBL_RADIX**|2|指数の基数|  
|**_DBL_ROUNDS**|1|加算の丸め: 近接|  
|**FLT_DIG**|6|有効桁数|  
|**FLT_EPSILON**|1.192092896e-07F|1.0+**FLT_EPSILON** !=1.0 のように最小|  
|**FLT_MANT_DIG**|24|仮数部のビット数|  
|**FLT_MAX**|3.402823466e+38F|最大値|  
|**FLT_MAX_10_EXP**|38|最大 10 進指数|  
|**FLT_MAX_EXP**|128|最大 2 進指数|  
|**FLT_MIN**|1.175494351e-38F|正の最小数|  
|**FLT_MIN_10_EXP**|(-37)|最小 10 進指数|  
|**FLT_MIN_EXP**|(-125)|最小 2 進指数|  
|**FLT_RADIX**|2|指数の基数|  
|**FLT_ROUNDS**|1|加算の丸め: 近接|  
  
## <a name="see-also"></a>参照  
 [グローバル定数](../c-runtime-library/global-constants.md)