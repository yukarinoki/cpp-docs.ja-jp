---
title: _variant_t::Detach |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::Detach
- _variant_t.Detach
dev_langs:
- C++
helpviewer_keywords:
- VARIANT object [C++], detatch
- Detach method [C++]
- VARIANT object
ms.assetid: c348ac08-62cf-4657-a16f-974a79c12158
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 42fc4bd5186ade5efaa9c4fa8e9f567f37509039
ms.sourcegitcommit: b92ca0b74f0b00372709e81333885750ba91f90e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/16/2018
ms.locfileid: "42571427"
---
# <a name="varianttdetach"></a>_variant_t::Detach
**Microsoft 固有の仕様**  
  
 カプセル化されたデタッチ`VARIANT`オブジェクトからこの`_variant_t`オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
VARIANT Detach( );  
```  
  
## <a name="return-value"></a>戻り値  
 カプセル化された`VARIANT`します。  
  
## <a name="remarks"></a>Remarks  
 抽出し、カプセル化された返します`VARIANT`、これをクリア`_variant_t`オブジェクトを破棄します。 このメンバー関数を削除、`VARIANT`カプセル化し、セットから、`VARTYPE`この`_variant_t`VT_EMPTY するオブジェクト。 返されたを解放するかどうかは`VARIANT`呼び出すことによって、 [VariantClear](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-variantclear)関数。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)