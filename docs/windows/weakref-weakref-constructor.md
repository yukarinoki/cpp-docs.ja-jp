---
title: Weakref::weakref コンス トラクター |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::WeakRef
dev_langs:
- C++
helpviewer_keywords:
- WeakRef, constructor
ms.assetid: 589f87e0-8dcc-4e82-aab2-f2f66f1ec47c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d7c8bc81040ce8d4c1cea7497f9d1371fbb9d41f
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42611611"
---
# <a name="weakrefweakref-constructor"></a>WeakRef::WeakRef コンストラクター

新しいインスタンスを初期化、 **WeakRef**クラス。

## <a name="syntax"></a>構文

```cpp
WeakRef();
WeakRef(
   decltype(__nullptr)  
);

WeakRef(
   _In_opt_ IWeakReference* ptr
);

WeakRef(
   const ComPtr<IWeakReference>& ptr
);

WeakRef(
   const WeakRef& ptr
);

WeakRef(
   _Inout_ WeakRef&& ptr
);
```

### <a name="parameters"></a>パラメーター

*ptr*  
ポインター、参照、または現在を初期化する既存のオブジェクトへの右辺値参照**WeakRef**オブジェクト。

## <a name="remarks"></a>Remarks

最初のコンス トラクターによって初期化空**WeakRef**オブジェクト。 2 番目のコンス トラクターによって初期化、 **WeakRef**オブジェクトへのポインターから、`IWeakReference`インターフェイス。 3 番目のコンス トラクターによって初期化、 **WeakRef**への参照からオブジェクトを`ComPtr<IWeakReference>`オブジェクト。 4 番目と 5 番目のコンス トラクターの初期化、 **WeakRef**から別のオブジェクト**WeakRef**オブジェクト。

## <a name="requirements"></a>要件

**ヘッダー:** client.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[WeakRef クラス](../windows/weakref-class.md)