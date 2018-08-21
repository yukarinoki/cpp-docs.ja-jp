---
title: Srwlock::lockshared メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockShared
dev_langs:
- C++
helpviewer_keywords:
- LockShared method
ms.assetid: 9d826a5c-b6a2-4430-ac85-d5753cbca889
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5fda64126709515fcf3e174a6f3cbdea22d5ee9e
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/09/2018
ms.locfileid: "40011063"
---
# <a name="srwlocklockshared-method"></a>SRWLock::LockShared メソッド
取得、 **SRWLock**共有モードでのオブジェクト。  
  
## <a name="syntax"></a>構文  
  
```cpp  
SyncLockShared LockShared();  
  
static SyncLockShared LockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 *lock*  
 ポインター、 **SRWLock**オブジェクト。  
  
## <a name="return-value"></a>戻り値  
 **SRWLock**共有モードでのオブジェクト。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [SRWLock クラス](../windows/srwlock-class.md)