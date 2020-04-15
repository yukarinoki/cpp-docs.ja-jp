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
ms.openlocfilehash: dc0d83f2550646572a4eff2bec7850037c6dbf6a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371335"
---
# <a name="makeallocator-class"></a>MakeAllocator クラス

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

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

*サポート*<br/>
弱い参照をサポートするオブジェクトにメモリを割り当てる場合は true、それより後の場合は**true。** 弱い参照をサポートしないオブジェクトにメモリを割り当てる場合は**false。**

## <a name="remarks"></a>解説

弱い参照サポートの有無にかかわらず、アクティブ化可能なクラスにメモリを割り当てます。

クラスを`MakeAllocator`オーバーライドして、ユーザー定義のメモリ割り当てモデルを実装します。

`MakeAllocator`通常は、構築中にオブジェクトがスローした場合にメモリ リークを防ぐために使用されます。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                                  | 説明
----------------------------------------------------- | ----------------------------------------------------------------
[メイクアロケーター::メイクアロケーター](#makeallocator)        | `MakeAllocator` クラスの新しいインスタンスを初期化します。
[メイクアロケーター::~メイクアロケーター](#tilde-makeallocator) | クラスの現在のインスタンスを初期化解除`MakeAllocator`します。

### <a name="public-methods"></a>パブリック メソッド

名前                                 | 説明
------------------------------------ | -----------------------------------------------------------------------------------------------------------
[メイクアロケーター::割り当て](#allocate) | メモリを割り当て、現在`MakeAllocator`のオブジェクトに関連付けます。
[メイクアロケーター::Dエタッハ](#detach)     | [Allocate](#allocate)メソッドによって割り当てられたメモリと現在`MakeAllocator`のオブジェクトの関連付けを解除します。

## <a name="inheritance-hierarchy"></a>継承階層

`MakeAllocator`

## <a name="requirements"></a>必要条件

**ヘッダー:** 実装.h

**名前空間:** マイクロソフト::WRL::Dのテール

## <a name="makeallocatorallocate"></a><a name="allocate"></a>メイクアロケーター::割り当て

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
__forceinline void* Allocate();
```

### <a name="return-value"></a>戻り値

成功した場合は、割り当てられたメモリへのポインタ。それ以外`nullptr`の場合は、 .

### <a name="remarks"></a>解説

メモリを割り当て、現在`MakeAllocator`のオブジェクトに関連付けます。

割り当てられたメモリのサイズは、現在`MakeAllocator`のテンプレート パラメーターで指定された型のサイズです。

開発者は、別のメモリ割`Allocate()`り当てモデルを実装するメソッドだけをオーバーライドする必要があります。

## <a name="makeallocatordetach"></a><a name="detach"></a>メイクアロケーター::Dエタッハ

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
__forceinline void Detach();
```

### <a name="remarks"></a>解説

[Allocate](#allocate)メソッドによって割り当てられたメモリと現在`MakeAllocator`のオブジェクトの関連付けを解除します。

を呼び`Detach()`出す場合は、`Allocate`メソッドによって提供されるメモリを削除する必要があります。

## <a name="makeallocatormakeallocator"></a><a name="makeallocator"></a>メイクアロケーター::メイクアロケーター

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
MakeAllocator();
```

### <a name="remarks"></a>解説

`MakeAllocator` クラスの新しいインスタンスを初期化します。

## <a name="makeallocatormakeallocator"></a><a name="tilde-makeallocator"></a>メイクアロケーター::~メイクアロケーター

WRL インフラストラクチャをサポートし、コードから直接使用するためのものではありません。

```cpp
~MakeAllocator();
```

### <a name="remarks"></a>解説

クラスの現在のインスタンスを初期化解除`MakeAllocator`します。

このデストラクターは、必要に応じて、基になる割り当て済みメモリも削除します。
