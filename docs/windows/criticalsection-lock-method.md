---
title: Criticalsection::lock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs:
- C++
helpviewer_keywords:
- Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4fedde29441c9c14b68dec5cff998be57d216e29
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42607661"
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock メソッド

指定されたクリティカル セクション オブジェクトの所有権を待機します。 呼び出し元のスレッドの所有権が付与されると、関数を返します。

## <a name="syntax"></a>構文

```cpp
SyncLock Lock();

   static SyncLock Lock(
   _In_ CRITICAL_SECTION* cs
);
```

### <a name="parameters"></a>パラメーター

*cs*  
ユーザー指定のクリティカル セクション オブジェクト。

## <a name="return-value"></a>戻り値

現在の重要なセクションのロック解除に使用できるロック オブジェクト。

## <a name="remarks"></a>Remarks

最初の**ロック**関数が現在のクリティカル セクション オブジェクトに影響します。 2 番目の**ロック**関数、ユーザー指定のクリティカル セクションに影響を与えます。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="see-also"></a>関連項目

[CriticalSection クラス](../windows/criticalsection-class.md)