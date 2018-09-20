---
title: Criticalsectiontraits::unlock メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleTraits::CriticalSectionTraits::Unlock
dev_langs:
- C++
helpviewer_keywords:
- Unlock method
ms.assetid: 8fb382f5-6eda-407e-9673-71d77bda4962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5babc5c14baae474409cd364af31b70549fcefe5
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46413017"
---
# <a name="criticalsectiontraitsunlock-method"></a>CriticalSectionTraits::Unlock メソッド

専門、`CriticalSection`その it サポート、クリティカル セクションを指定したオブジェクトの所有権を解放するためのテンプレート。

## <a name="syntax"></a>構文

```cpp
inline static void Unlock(
   _In_ Type cs
);
```

### <a name="parameters"></a>パラメーター

*cs*<br/>
クリティカル セクション オブジェクトへのポインター。

## <a name="remarks"></a>Remarks

`Type`として修飾子が定義されている`typedef CRITICAL_SECTION* Type;`します。

詳細については、次を参照してください。**により関数**で、**同期関数**Windows API のドキュメントの「します。

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers::HandleTraits

## <a name="see-also"></a>関連項目

[CriticalSectionTraits 構造体](../windows/criticalsectiontraits-structure.md)