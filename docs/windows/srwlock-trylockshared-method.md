---
title: Srwlock::trylockshared メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockShared
dev_langs:
- C++
helpviewer_keywords:
- TryLockShared method
ms.assetid: 10cc198d-39a0-4d18-aa78-706744948668
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 289fa1fbec61140e213bef7219e440c8177e19e5
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645813"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared メソッド
取得を試みる、 **SRWLock**オブジェクトの現在または指定した共有モードで**SRWLock**オブジェクト。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *lock*  
 ポインター、 **SRWLock**オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、 **SRWLock**共有モードと呼び出し元のスレッド内のオブジェクトは、ロックの所有権を取得します。 それ以外の場合、 **SRWLock**オブジェクトの状態が無効です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [SRWLock クラス](../windows/srwlock-class.md)