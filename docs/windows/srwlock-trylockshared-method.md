---
title: Srwlock::trylockshared メソッド |Microsoft ドキュメント
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
ms.openlocfilehash: 19ff9324f946f48f201678f9c9e7403ba774b2c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892284"
---
# <a name="srwlocktrylockshared-method"></a>SRWLock::TryLockShared メソッド
現在または指定した SRWLock オブジェクトの共有モードで SRWLock オブジェクトを取得しようとしています。  
  
## <a name="syntax"></a>構文  
  
```  
WRL_NOTHROW SyncLockShared TryLockShared();  
WRL_NOTHROW static SyncLockShared TryLockShared(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `lock`  
 SRWLock オブジェクトへのポインター。  
  
## <a name="return-value"></a>戻り値  
 成功した場合、共有モードと呼び出し元のスレッドで SRWLock オブジェクトは、ロックの所有権を取得します。 それ以外の場合、SRWLock オブジェクトの状態が無効です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
 [SRWLock クラス](../windows/srwlock-class.md)