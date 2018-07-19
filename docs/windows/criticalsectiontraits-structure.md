---
title: CriticalSectionTraits 構造体 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits
dev_langs:
- C++
helpviewer_keywords:
- CriticalSectionTraits structure
ms.assetid: c515a1b5-4eb0-40bc-9035-c4d9352c9de7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5534173d594b8fc09ceca8ec44a1c1223bc550b2
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33870552"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 構造体
無効な重要なセクションまたはリリースの重要なセクションに関数のいずれかをサポートするために CriticalSection オブジェクトを専門としています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|A`typedef`クリティカル セクションへのポインターを定義します。 `Type` 見なさ`typedef CRITICAL_SECTION* Type;`です。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue メソッド](../windows/criticalsectiontraits-getinvalidvalue-method.md)|CriticalSection テンプレートを特化できるように、テンプレートは、常に有効です。|  
|[CriticalSectionTraits::Unlock メソッド](../windows/criticalsectiontraits-unlock-method.md)|指定されたクリティカル セクション オブジェクトの解放の所有権をサポートするように CriticalSection テンプレートを専門としています。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)