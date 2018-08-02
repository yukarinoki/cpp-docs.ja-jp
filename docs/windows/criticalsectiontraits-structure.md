---
title: CriticalSectionTraits 構造体 |Microsoft Docs
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
ms.openlocfilehash: 8b10d130190308520771e37e97d34238f75670ad
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466684"
---
# <a name="criticalsectiontraits-structure"></a>CriticalSectionTraits 構造体
無効なクリティカル セクションまたはクリティカル セクションを解放する関数をサポートする CriticalSection オブジェクトを専門としています。  
  
## <a name="syntax"></a>構文  
  
```  
struct CriticalSectionTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|A **typedef**クリティカル セクションを指すポインターを定義します。 `Type` 見なさ`typedef CRITICAL_SECTION* Type;`します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[CriticalSectionTraits::GetInvalidValue メソッド](../windows/criticalsectiontraits-getinvalidvalue-method.md)|専門、`CriticalSection`テンプレート、テンプレートが常に有効なされないようにします。|  
|[CriticalSectionTraits::Unlock メソッド](../windows/criticalsectiontraits-unlock-method.md)|専門、`CriticalSection`その it サポート、クリティカル セクションを指定したオブジェクトの所有権を解放するためのテンプレート。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `CriticalSectionTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)