---
title: SRWLockExclusiveTraits 構造体 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits
dev_langs:
- C++
helpviewer_keywords:
- SRWLockExclusiveTraits structure
ms.assetid: 38a996ef-c2d7-4886-b413-a426ecee8f05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49f1f50b3fa9e34da8831c1cec138b6aefec27a5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39649274"
---
# <a name="srwlockexclusivetraits-structure"></a>SRWLockExclusiveTraits 構造体
一般的な特性について説明します、`SRWLock`排他ロック モードでのクラス。  
  
## <a name="syntax"></a>構文  
  
```  
struct SRWLockExclusiveTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLockExclusiveTraits::GetInvalidValue メソッド](../windows/srwlockexclusivetraits-getinvalidvalue-method.md)|取得、 **SRWLockExclusiveTraits**オブジェクトは常に有効です。|  
|[SRWLockExclusiveTraits::Unlock メソッド](../windows/srwlockexclusivetraits-unlock-method.md)|指定したの排他的制御を解放`SRWLock`オブジェクト。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLockExclusiveTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)