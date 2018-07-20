---
title: Semaphore::lock メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 0eef6ede-dc7d-4f09-a6c8-2f7d39d65bfa
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 80b4db212236da6c9fb320ff5a5e04f4e9f4a4c6
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892476"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock メソッド
指定されたタイムアウト期間が経過したか、現在のオブジェクトか、指定したハンドルに関連付けられているセマフォ オブジェクトになるまで待機がシグナル状態になっています。  
  
## <a name="syntax"></a>構文  
  
```  
SyncLock Lock(  
   DWORD milliseconds = INFINITE  
);  
  
static SyncLock Lock(  
   HANDLE h,  
   DWORD milliseconds = INFINITE  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `milliseconds`  
 タイムアウト間隔 (ミリ秒単位)。 既定値は、無限で、無期限に待機します。  
  
 `h`  
 セマフォ オブジェクトへのハンドル。  
  
## <a name="return-value"></a>戻り値  
 Details::SyncLockWithStatusT\<HandleTraits::SemaphoreTraits >  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** corewrappers.h  
  
 **Namespace:** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>関連項目  
[Semaphore クラス](../windows/semaphore-class.md)
 