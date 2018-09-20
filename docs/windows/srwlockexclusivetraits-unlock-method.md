---
title: Srwlockexclusivetraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::SRWLockExclusiveTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 7fd6b0fb-8b88-4a43-aa74-0d7fe47a0da6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: cf16b1ed7d7e344665733caeb56670d503dc4a88
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46399458"
---
# <a name="srwlockexclusivetraitsunlock-method"></a>SRWLockExclusiveTraits::Unlock メソッド

指定したの排他的制御を解放`SRWLock`オブジェクト。

## <a name="syntax"></a>構文

```cpp
inline static void Unlock(
   _In_ Type srwlock
);
```

### <a name="parameters"></a>パラメーター

*srwlock*<br/>
ハンドル、`SRWLock`オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[SRWLockExclusiveTraits 構造体](../windows/srwlockexclusivetraits-structure.md)