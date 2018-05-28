---
title: SRWLockSharedTraits 構造体 |Microsoft ドキュメント
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
ms.openlocfilehash: 6a18edef3fa658608459244143a5e48738f0c3a9
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="srwlocksharedtraits-structure"></a>SRWLockSharedTraits 構造体
SRWLock クラス共有ロック モードでの一般的な特徴をについて説明します。  
  
## <a name="syntax"></a>構文  
  
```  
struct SRWLockSharedTraits;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`Type`|ポインターのシノニム、 [SRWLOCK](../windows/srwlock-class.md)クラスです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[SRWLockSharedTraits::GetInvalidValue メソッド](../windows/srwlocksharedtraits-getinvalidvalue-method.md)|常に有効ではない SRWLockSharedTraits オブジェクトを取得します。|  
|[SRWLockSharedTraits::Unlock メソッド](../windows/srwlocksharedtraits-unlock-method.md)|指定した SRWLock オブジェクトの排他的に制御を解放します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `SRWLockSharedTraits`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Wrappers::HandleTraits 名前空間](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)