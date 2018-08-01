---
title: 浮動小数点の制限 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- float.h header file
- limits, floating-point constants
- floating-point numbers [C++]
- floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a111d2ea3e8e5503754b0d9c0c1a4f69170a41c
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39401760"
---
# <a name="floating-limits"></a>浮動小数点の制限
**Microsoft 固有の仕様**  
  
 次の表に、浮動小数点定数の値に関する制限を示します。 これらの制限が、標準ヘッダー ファイルで定義されても\<float.h >。  
  
### <a name="limits-on-floating-point-constants"></a>浮動小数点定数の制限  
  
|定数|説明|[値]|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|q 桁の浮動小数点数を、精度を失わずに丸めて浮動小数点表現にしたり、戻したりできる桁数 q。|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|x + 1.0 が 1.0 に等しくならないような最小の正数 x。|1.192092896e-07F 2.2204460492503131e-016 2.2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|浮動小数点の有効桁で FLT_RADIX により指定された基数の桁数。 基数は 2 です。そのためこれらの値はビットを指定します。|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|表現可能な最大浮動小数点数。|3.402823466e+38F 1.7976931348623158e+308 1.7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|最大の整数をその数値 10 が発生した結果が表現可能な浮動小数点数です。|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|FLT_RADIX をその数値分累乗した結果が表現可能な浮動小数点数となる最大の整数。|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|正の最小数。|1.175494351e-38 f 2.2250738585072014e-308 2.2250738585072014e-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|最小の負の整数をその数値 10 が発生した結果が表現可能な浮動小数点数です。|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|FLT_RADIX をその数値分累乗した結果が表現可能な浮動小数点数となる最小の負の整数。|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|指数表記の基数。|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|浮動小数点加算の丸めモード。|1 (近く) 1 (近く) 1 (近く)|  
  
> [!NOTE]
>  この表の情報は、将来のバージョンの製品では異なる場合があります。  
  
**Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [整数の制限](../cpp/integer-limits.md)