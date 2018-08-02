---
title: _variant_t::SetString |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- _variant_t::SetString
dev_langs:
- C++
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 090fd7ed027738ebe7bc9276e3b3f124b9212c4a
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463468"
---
# <a name="varianttsetstring"></a>_variant_t::SetString
**Microsoft 固有の仕様**  
  
 この `_variant_t` オブジェクトに文字列を代入します。  
  
## <a name="syntax"></a>構文  
  
```  
void SetString(const char* pSrc);  
```  
  
#### <a name="parameters"></a>パラメーター  
 *pSrc*  
 文字列へのポインター。  
  
## <a name="remarks"></a>Remarks  
 ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>関連項目  
 [_variant_t クラス](../cpp/variant-t-class.md)