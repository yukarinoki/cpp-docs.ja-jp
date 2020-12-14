---
description: '詳細情報: 浮動小数点の制限'
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
ms.openlocfilehash: 92694ee605d7cec12d03d808168b095f5c9f447b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242588"
---
# <a name="floating-limits"></a>浮動小数点の制限

**Microsoft 固有の仕様**

次の表に、浮動小数点定数の値に関する制限を示します。 これらの制限は、標準ヘッダーファイルでも定義されてい \<float.h> ます。

## <a name="limits-on-floating-point-constants"></a>浮動小数点定数の制限

|定数|説明|[値]|
|--------------|-------------|-----------|
|`FLT_DIG`<br/>`DBL_DIG`<br/>`LDBL_DIG`|q 桁の浮動小数点数を、精度を失わずに丸めて浮動小数点表現にしたり、戻したりできる桁数 q。|6<br/>15<br/>15|
|`FLT_EPSILON`<br/>`DBL_EPSILON`<br/>`LDBL_EPSILON`|x + 1.0 が 1.0 に等しくならないような最小の正数 x。|1.192092896e-07F<br/>2.2204460492503131e-016<br/>2.2204460492503131e-016|
|`FLT_GUARD`||0|
|`FLT_MANT_DIG`<br/>`DBL_MANT_DIG`<br/>`LDBL_MANT_DIG`|浮動小数点有効桁ので指定された基数の桁数 `FLT_RADIX` 。 基数は2です。したがって、これらの値はビットを指定します。|24<br/>53<br/>53|
|`FLT_MAX`<br/>`DBL_MAX`<br/>`LDBL_MAX`|表現可能な最大浮動小数点数。|3.402823466e+38F<br/>1.7976931348623158e+308<br/>1.7976931348623158e+308|
|`FLT_MAX_10_EXP`<br/>`DBL_MAX_10_EXP`<br/>`LDBL_MAX_10_EXP`|その数値に対して生成された10が表現可能な浮動小数点数である、最大の整数。|38<br/>308<br/>308|
|`FLT_MAX_EXP`<br/>`DBL_MAX_EXP`<br/>`LDBL_MAX_EXP`|この `FLT_RADIX` 数値に発生する最大整数は表現可能な浮動小数点数です。|128<br/>1024<br/>1024|
|`FLT_MIN`<br/>`DBL_MIN`<br/>`LDBL_MIN`|正の最小数。|1.175494351e-38F<br/>2.2250738585072014e-308<br/>2.2250738585072014e-308|
|`FLT_MIN_10_EXP`<br/>`DBL_MIN_10_EXP`<br/>`LDBL_MIN_10_EXP`|10をその数値に累乗した値が表現可能な浮動小数点数である、最小の負の整数。|-37<br/>-307<br/>-307|
|`FLT_MIN_EXP`<br/>`DBL_MIN_EXP`<br/>`LDBL_MIN_EXP`|この数値に発生した最小の負の整数 `FLT_RADIX` は表現可能な浮動小数点数です。|-125<br/>-1021<br/>-1021|
|`FLT_NORMALIZE`||0|
|`FLT_RADIX`<br/>`_DBL_RADIX`<br/>`_LDBL_RADIX`|指数表記の基数。|2<br/>2<br/>2|
|`FLT_ROUNDS`<br/>`_DBL_ROUNDS`<br/>`_LDBL_ROUNDS`|浮動小数点加算の丸めモード。|1 (近接)<br/>1 (近接)<br/>1 (近接)|

> [!NOTE]
> この表の情報は、将来のバージョンの製品では異なる場合があります。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[整数の制限](../cpp/integer-limits.md)
