---
title: Semaphore::lock メソッド |Microsoft Docs
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
ms.openlocfilehash: 47925bcc647d253775e4dd61f6a7f5d5fb586dde
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42599284"
---
# <a name="semaphorelock-method"></a>Semaphore::Lock メソッド

現在のオブジェクトまでの待機、または**セマフォ**オブジェクトに関連付けられている指定したハンドルがシグナル状態で、または指定されたタイムアウト期間が経過しました。

## <a name="syntax"></a>構文

```cpp
SyncLock Lock(
   DWORD milliseconds = INFINITE
);

static SyncLock Lock(
   HANDLE h,
   DWORD milliseconds = INFINITE
);
```

### <a name="parameters"></a>パラメーター

*(ミリ秒)*  
タイムアウト間隔 (ミリ秒単位)。 既定値は、INFINITE で、無期限に待機します。

*h*  
識別するハンドルを**セマフォ**オブジェクト。

## <a name="return-value"></a>戻り値

`Details::SyncLockWithStatusT<HandleTraits::SemaphoreTraits>`。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[Semaphore クラス](../windows/semaphore-class.md)