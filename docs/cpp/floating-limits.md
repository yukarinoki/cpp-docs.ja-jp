---
title: 浮動小数点の制限
ms.date: 08/03/2018
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
ms.openlocfilehash: ccd395eef319e57cecffad8a5278b6df1397f4cb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373377"
---
# <a name="floating-limits"></a>浮動小数点の制限

**マイクロソフト固有**

次の表に、浮動小数点定数の値に関する制限を示します。 これらの制限は、標準ヘッダファイル\<float.h>でも定義されます。

## <a name="limits-on-floating-point-constants"></a>浮動小数点定数の制限

|定数|意味|[値]|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|q 桁の浮動小数点数を、精度を失わずに丸めて浮動小数点表現にしたり、戻したりできる桁数 q。|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|x + 1.0 が 1.0 に等しくならないような最小の正数 x。|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|浮動小数点の意味で指定された`FLT_RADIX`基数の桁数。 基数は 2 です。したがって、これらの値はビットを指定します。|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|最大表現可能な浮動小数点数。|3.402823466e+38F<br/>1.7976931348623158e+308<br/>1.7976931348623158e+308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|その数値に 10 を引き上げる最大整数は、表現可能な浮動小数点数です。|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|その数値に`FLT_RADIX`上げられた整数の最大値は、表現可能な浮動小数点数です。|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|正の最小数。|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|その数値に 10 を引き上げる最小負の整数は、表現可能な浮動小数点数です。|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|その数値に`FLT_RADIX`上げられた最小負の整数は、表現可能な浮動小数点数です。|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|指数表記の基数。|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|浮動小数点加算の丸めモード。|1 (近接)<br/>1 (近接)<br/>1 (近接)|

> [!NOTE]
> この表の情報は、将来のバージョンの製品では異なる場合があります。

**エンド マイクロソフト 固有**

## <a name="see-also"></a>関連項目

[整数の制限](../cpp/integer-limits.md)
