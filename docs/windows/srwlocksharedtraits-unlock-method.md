---
title: Srwlocksharedtraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockSharedTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 33cdead9-1900-4094-b18e-38fcf1a0bd28
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a8c8567a63a3ae7e2ffb0c23e99715d63fe7b20a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46427096"
---
# <a name="srwlocksharedtraitsunlock-method"></a>SRWLockSharedTraits::Unlock メソッド

指定したの排他的制御を解放`SRWLock`オブジェクト。

## <a name="syntax"></a>構文

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
識別するハンドルを`SRWLock`オブジェクト。

## <a name="return-value"></a>戻り値

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[SRWLockSharedTraits 構造体](../windows/srwlocksharedtraits-structure.md)