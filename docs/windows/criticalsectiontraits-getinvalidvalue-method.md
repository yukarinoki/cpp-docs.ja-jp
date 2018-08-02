---
title: Criticalsectiontraits::getinvalidvalue メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::GetInvalidValue
dev_langs:
- C++
helpviewer_keywords:
- GetInvalidValue method
ms.assetid: 665f30a6-ca9c-4968-8c03-8f84e6b2329b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf0d52769052a36c0b494d19204dd6c07f0b2404
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463386"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue メソッド
専門、 **CriticalSection**テンプレート、テンプレートが常に有効なされないようにします。  
  
## <a name="syntax"></a>構文  
  
```  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>戻り値  
 常に無効な重要なセクションにポインターを返します。  
  
## <a name="remarks"></a>Remarks  
 *型*として修飾子が定義されている`typedef CRITICAL_SECTION* Type;`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)