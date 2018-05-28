---
title: 数値演算エラー定数 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: conceptual
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
dev_langs:
- C++
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb491e8073acf2af525814b595ce79365df0fa1
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="math-error-constants"></a>数値演算エラー定数
## <a name="syntax"></a>構文  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>コメント  
 ランタイム ライブラリの数値演算ルーチンでは、数値演算エラー定数が生成されることがあります。  
  
 次に記載するこれらのエラーは、MATH.H で定義されている例外の種類に対応し、数値演算エラーが発生したときに `_matherr` 関数によって返されます。  
  
|定数|説明|  
|--------------|-------------|  
|`_DOMAIN`|関数の引数が、関数の定義域外です。|  
|`_OVERFLOW`|関数の戻り値の型で表現するには結果が大きすぎます。|  
|`_PLOSS`|有効桁の部分的損失が発生しました。|  
|`_SING`|引数の特異点: 関数への引数が無効な値です。 (たとえば、値 0 は 0 以外の値を必要とする関数に渡されます。)|  
|`_TLOSS`|有効桁の完全損失が発生しました。|  
|`_UNDERFLOW`|結果が小さすぎて表現できません。|  
  
## <a name="see-also"></a>参照  
 [_matherr](../c-runtime-library/reference/matherr.md)   
 [グローバル定数](../c-runtime-library/global-constants.md)