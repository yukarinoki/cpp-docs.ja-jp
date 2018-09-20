---
title: MakeAllocator クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
dev_langs:
- C++
helpviewer_keywords:
- MakeAllocator class
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 460e2cdef4d0ba4252ceb8a4b7fe6defc25c183a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46375374"
---
# <a name="makeallocator-class"></a>MakeAllocator クラス

WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。

## <a name="syntax"></a>構文

```cpp
template<
   typename T,
   bool hasWeakReferenceSupport =
         !__is_base_of(RuntimeClassFlags<InhibitWeakReference>, T)>
class MakeAllocator;

template<typename T>
class MakeAllocator<T, false>;

template<typename T>
class MakeAllocator<T, true>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
型の名前。

*hasWeakReferenceSupport*<br/>
**true**弱い参照は; をサポートするオブジェクトのメモリを割り当てられません。**false**弱い参照をサポートしていないオブジェクトのメモリを割り当てられません。

## <a name="remarks"></a>Remarks

弱い参照のサポートの有無のアクティブ化可能なクラスのメモリを割り当てます。

上書き、 **MakeAllocator**ユーザー定義のメモリ割り当てモデルを実装するクラス。

**MakeAllocator**は通常、構築時にオブジェクトをスローした場合は、メモリ リークを防ぐために使用します。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[MakeAllocator::MakeAllocator コンストラクター](../windows/makeallocator-makeallocator-constructor.md)|新しいインスタンスを初期化、 **MakeAllocator**クラス。|
|[MakeAllocator::~MakeAllocator デストラクター](../windows/makeallocator-tilde-makeallocator-destructor.md)|現在のインスタンスの初期化を解除、 **MakeAllocator**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[MakeAllocator::Allocate メソッド](../windows/makeallocator-allocate-method.md)|メモリを割り当て、現在のそれに**MakeAllocator**オブジェクト。|
|[MakeAllocator::Detach メソッド](../windows/makeallocator-detach-method.md)|によって割り当てられたメモリの関連付けを解除、 [Allocate](../windows/makeallocator-allocate-method.md)メソッドは、現在から**MakeAllocator**オブジェクト。|

## <a name="inheritance-hierarchy"></a>継承階層

`MakeAllocator`

## <a name="requirements"></a>要件

**ヘッダー:** implements.h

**Namespace:** Microsoft::WRL::Details

## <a name="see-also"></a>関連項目

[Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)