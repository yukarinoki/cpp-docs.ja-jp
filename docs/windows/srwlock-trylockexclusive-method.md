---
title: Srwlock::trylockexclusive メソッド |Microsoft Docs
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
ms.openlocfilehash: 2ec8275b1db692410677276e762f79ccf23548cc
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42606232"
---
# <a name="srwlocktrylockexclusive-method"></a>SRWLock::TryLockExclusive メソッド

取得を試みる、 **SRWLock**オブジェクトの現在または指定された排他モードで**SRWLock**オブジェクト。 呼び出しが成功した場合、呼び出し元のスレッドはロックの所有権を取得します。

## <a name="syntax"></a>構文

```cpp
SyncLockExclusive TryLockExclusive();

static SyncLockExclusive TryLockExclusive(
   _In_ SRWLOCK* lock
);
```

### <a name="parameters"></a>パラメーター

*lock*  
ポインター、 **SRWLock**オブジェクト。

## <a name="return-value"></a>戻り値

成功した場合、 **SRWLock**排他モードと呼び出し元のスレッド内のオブジェクトは、ロックの所有権を取得します。 それ以外の場合、 **SRWLock**オブジェクトの状態が無効です。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[SRWLock クラス](../windows/srwlock-class.md)