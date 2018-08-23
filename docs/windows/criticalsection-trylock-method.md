---
title: Criticalsection::trylock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::TryLock
dev_langs:
- C++
helpviewer_keywords:
- TryLock method
ms.assetid: 504bb87c-2cd0-4f54-b458-b3efb9789053
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 382dbdd2d0816d6ab0846acd0f8c164cd542114f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42575842"
---
# <a name="criticalsectiontrylock-method"></a>CriticalSection::TryLock メソッド

ブロックすることがなく、クリティカル セクションを入力しようとします。 呼び出しが成功した場合、呼び出し元のスレッドはクリティカル セクションの所有権を取得します。

## <a name="syntax"></a>構文

```cpp
SyncLock TryLock();

static SyncLock TryLock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*cs*  
ユーザー指定のクリティカル セクション オブジェクト。

## <a name="return-value"></a>戻り値

クリティカル セクションが正しく入力された場合は 0 以外の値または現在のスレッドはクリティカル セクションを既に所有しています。 別のスレッドがクリティカル セクション既に所有している場合は 0 します。

## <a name="remarks"></a>Remarks

最初の**TryLock**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目の**TryLock**関数、ユーザー指定のクリティカル セクションに影響を与えます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[CriticalSection クラス](../windows/criticalsection-class.md)