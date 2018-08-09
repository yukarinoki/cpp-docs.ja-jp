---
title: SRWLockSharedTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockSharedTraits structure
ms.assetid: 709cb51e-d70c-40b6-bdb4-d8eacf3af495
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db9a16671be21b2df7a4ce4f9d87a8b66e097e33
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020149"
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体
一般的な特性について説明します、`SRWLock`共有ロック モードでのクラス。  
  
## <a name="syntax"></a>構文  
  
```cpp  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue メソッド](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|取得、 **SRWLockSharedTraits**オブジェクトは常に有効です。|  
|[SRWLockSharedTraits::Unlock メソッド](../windows/srwlocksharedtraits-unlock-method.md)|指定したの排他的制御を解放`SRWLock`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)