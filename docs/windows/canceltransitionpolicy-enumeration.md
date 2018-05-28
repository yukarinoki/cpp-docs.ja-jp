---
title: CancelTransitionPolicy 列挙型 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
dev_langs:
- C++
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f588e67066fed690271aa7d78fcbe726c67177
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy 列挙型
どの非同期操作しようのターミナル状態に移行することを示します。 完了するか、クライアントが要求の取り消された状態に関してエラーが動作する必要があります。  
  
## <a name="syntax"></a>構文  
  
```  
enum CancelTransitionPolicy;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="values"></a>値  
  
|名前|説明|  
|----------|-----------------|  
|`RemainCanceled`|非同期操作は、クライアントが要求の取り消された状態では現在の場合は、完了したターミナルまたはエラー状態に遷移するのではなく、取り消された状態にそのまま残ることを示します。|  
|`TransitionFromCanceled`|状態が取り消された状態の終了状態が完了したを移行する必要があることを示しますこの場合は、非同期操作は、クライアントが要求の取り消された状態では現在、またはこのフラグを使用する呼び出しによって決定されるエラー。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** async.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)