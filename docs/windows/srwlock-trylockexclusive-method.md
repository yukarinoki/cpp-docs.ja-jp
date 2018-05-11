---
title: Srwlock::trylockexclusive メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::SRWLock::TryLockExclusive
dev_langs:
- C++
helpviewer_keywords:
- TryLockExclusive method
ms.assetid: 661e8b19-3058-4511-8742-c9fbb90412c7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1cc9ee8a63d7403c3de408c924eeab07f1d0efa1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive メソッド
現在または指定した SRWLock オブジェクトの排他モードで SRWLock オブジェクトを取得しようとしています。 呼び出しが成功した場合、呼び出し元スレッドは、ロックの所有権を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLockExclusive TryLockExclusive();  
  
static SyncLockExclusive TryLockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lock`  
 SRWLock オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、排他モードと呼び出し元のスレッドで SRWLock オブジェクトは、ロックの所有権を取得します。 それ以外の場合、SRWLock オブジェクトの状態が無効です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [SRWLock クラス](../windows/srwlock-class.md)