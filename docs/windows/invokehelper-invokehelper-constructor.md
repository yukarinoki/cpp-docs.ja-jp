---
title: Invokehelper::invokehelper コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::InvokeHelper::InvokeHelper
dev_langs:
- C++
helpviewer_keywords:
- InvokeHelper, constructor
ms.assetid: 0223c574-abc3-4fc0-99e6-38626ba79243
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 11f3e82f0834863c3cdfb476443a4dbd0bdf1f6f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46385080"
---
# <a name="invokehelperinvokehelper-constructor"></a>InvokeHelper::InvokeHelper コンストラクター

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
explicit InvokeHelper(
   TCallback callback
);
```

### <a name="parameters"></a>パラメーター

*コールバック*<br/>
イベント ハンドラー。

## <a name="remarks"></a>Remarks

新しいインスタンスを初期化、 **InvokeHelper**クラス。

`TCallback`テンプレート パラメーターは、イベント ハンドラーの種類を指定します。

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[InvokeHelper 構造体](../windows/invokehelper-structure.md)<br/>
[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)