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
ms.openlocfilehash: 01efd9bf3941a5b19e1f0fe6c106d47f1b6e9fcf
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39642062"
---
# <a name="criticalsectiontraitsgetinvalidvalue-method"></a>CriticalSectionTraits::GetInvalidValue メソッド
専門、 **CriticalSection**テンプレート、テンプレートが常に有効なされないようにします。  
  
## <a name="syntax"></a>構文  
  
```cpp  
inline static Type GetInvalidValue();  
```  
  
## <a name="return-value"></a>戻り値  
 常に無効な重要なセクションにポインターを返します。  
  
## <a name="remarks"></a>Remarks  
 `Type`として修飾子が定義されている`typedef CRITICAL_SECTION* Type;`します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)