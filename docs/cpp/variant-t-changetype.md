---
title: _variant_t::ChangeType |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::ChangeType
- _variant_t.ChangeType
dev_langs:
- C++
helpviewer_keywords:
- ChangeType method [C++]
- VARIANT object [C++], ChangeType
- VARIANT object
ms.assetid: 829d2eeb-3338-4a88-9dce-0ca145f47aac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5f3790f4cb357ed830ba2c61b3c2906356dc64da
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465589"
---
# <a name="varianttchangetype"></a>_variant_t::ChangeType
**Microsoft 固有の仕様**  
  
 型を変更、`_variant_t`オブジェクトを指定された`VARTYPE`します。  
  
## <a name="syntax"></a>構文  
  
```  
void ChangeType(  
   VARTYPE vartype,  
   const _variant_t* pSrc = NULL   
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *vartype*  
 `VARTYPE`この`_variant_t`オブジェクト。  
  
 *pSrc*  
 変換する `_variant_t` オブジェクトへのポインター。 この値が NULL の場合は、変換が適切に実行されます。  
  
## <a name="remarks"></a>Remarks  
 このメンバー関数に変換する`_variant_t`オブジェクトを指定された`VARTYPE`します。 場合*pSrc*が NULL の場合、変換が行われる場所、それ以外の場合にこの`_variant_t`からオブジェクトをコピー *pSrc*変換と。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)