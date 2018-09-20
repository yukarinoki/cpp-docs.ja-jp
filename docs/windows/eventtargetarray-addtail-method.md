---
title: Eventtargetarray::addtail メソッド |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ab0219c8893ff7ad35e29f9dd8b18be18caf8eb9
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378125"
---
# <a name="eventtargetarrayaddtail-method"></a>EventTargetArray::AddTail メソッド

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
void AddTail(
   _In_ IUnknown* element
);
```

### <a name="parameters"></a>パラメーター

*要素*<br/>
追加するイベント ハンドラーへのポインター。

## <a name="remarks"></a>Remarks

イベント ハンドラーの内部配列の末尾には、指定したイベント ハンドラーを追加します。

**AddTail()** によって内部的にのみ使用するものでは、`EventSource`クラス。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[EventTargetArray クラス](../windows/eventtargetarray-class.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)