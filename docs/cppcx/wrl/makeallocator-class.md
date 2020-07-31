---
title: MakeAllocator クラス
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::Allocate
- implements/Microsoft::WRL::Details::MakeAllocator::Detach
- implements/Microsoft::WRL::Details::MakeAllocator::MakeAllocator
- implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
helpviewer_keywords:
- Microsoft::WRL::Details::MakeAllocator class
- Microsoft::WRL::Details::MakeAllocator::Allocate method
- Microsoft::WRL::Details::MakeAllocator::Detach method
- Microsoft::WRL::Details::MakeAllocator::MakeAllocator, constructor
- Microsoft::WRL::Details::MakeAllocator::~MakeAllocator, destructor
ms.assetid: a1114615-abd7-4a56-9bc3-750c118f0fa1
ms.openlocfilehash: 19d3ab294df8adc059424c97e5733ae9ebb75c9c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218378"
---
# <a name="makeallocator-class"></a>MakeAllocator クラス

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

## <a name="syntax"></a>構文

```cpp
template<
    typename T,
    bool hasWeakReferenceSupport =
          !__is_base_of(RuntimeClassFlags<InhibitWeakReference>,
                        T)
>
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
**`true`** 弱参照をサポートするオブジェクトにメモリを割り当てるには**`false`** 弱い参照をサポートしていないオブジェクトにメモリを割り当てる場合は。

## <a name="remarks"></a>解説

弱い参照をサポートするか、または使用せずに、アクティブ化可能なクラスにメモリを割り当てます。

クラスをオーバーライドし `MakeAllocator` て、ユーザー定義のメモリ割り当てモデルを実装します。

`MakeAllocator`は通常、構築中にオブジェクトがをスローした場合にメモリリークを防ぐために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                  | 説明
----------------------------------------------------- | ----------------------------------------------------------------
[MakeAllocator:: MakeAllocator](#makeallocator)        | `MakeAllocator` クラスの新しいインスタンスを初期化します。
[MakeAllocator:: ~ MakeAllocator](#tilde-makeallocator) | クラスの現在のインスタンスを初期化解除 `MakeAllocator` します。

### <a name="public-methods"></a>パブリック メソッド

名前                                 | 説明
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[MakeAllocator:: Allocate](#allocate) | メモリを割り当てて、現在のオブジェクトに関連付け `MakeAllocator` ます。
[MakeAllocator::D します。](#detach)     | 現在のオブジェクトから、 [Allocate](#allocate)メソッドによって割り当てられたメモリの関連付けを解除 `MakeAllocator` します。

## <a name="inheritance-hierarchy"></a>継承階層

`MakeAllocator`

## <a name="requirements"></a>必要条件

**Header:** を実装します。

**名前空間:** Microsoft:: WRL::D etails

## <a name="makeallocatorallocate"></a><a name="allocate"></a>MakeAllocator:: Allocate

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>戻り値

成功した場合は、割り当てられたメモリへのポインター。それ以外の場合は **`nullptr`** 。

### <a name="remarks"></a>解説

メモリを割り当てて、現在のオブジェクトに関連付け `MakeAllocator` ます。

割り当てられたメモリのサイズは、現在のテンプレートパラメーターによって指定された型のサイズです `MakeAllocator` 。

開発者は、メソッドのみをオーバーライドして、 `Allocate()` 異なるメモリ割り当てモデルを実装する必要があります。

## <a name="makeallocatordetach"></a><a name="detach"></a>MakeAllocator::D します。

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>解説

現在のオブジェクトから、 [Allocate](#allocate)メソッドによって割り当てられたメモリの関連付けを解除 `MakeAllocator` します。

を呼び出すと `Detach()` 、メソッドによって提供されるメモリを削除する責任があり `Allocate` ます。

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a>MakeAllocator:: MakeAllocator

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
MakeAllocator();
```

### <a name="remarks"></a>解説

`MakeAllocator` クラスの新しいインスタンスを初期化します。

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a>MakeAllocator:: ~ MakeAllocator

は WRL インフラストラクチャをサポートします。独自に作成したコードから直接使用するためのものではありません。

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除 `MakeAllocator` します。

このデストラクターは、必要に応じて、割り当てられている基になるメモリも削除します。
