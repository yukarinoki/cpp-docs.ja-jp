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
ms.openlocfilehash: 6609bba6d7adbddda152007e4db45c82f8039bc0
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603679"
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

*要素*  
追加するイベント ハンドラーへのポインター。

## <a name="remarks"></a>Remarks

イベント ハンドラーの内部配列の末尾には、指定したイベント ハンドラーを追加します。

**AddTail()** によって内部的にのみ使用するものでは、`EventSource`クラス。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[EventTargetArray クラス](../windows/eventtargetarray-class.md)  
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)