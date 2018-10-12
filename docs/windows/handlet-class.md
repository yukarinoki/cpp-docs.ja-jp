---
title: HandleT クラス |Microsoft Docs
ms.custom: ''
ms.date: 10/03/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Attach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Close
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Get
- corewrappers/Microsoft::WRL::Wrappers::HandleT::handle_
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
- corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
- corewrappers/Microsoft::WRL::Wrappers::HandleT::IsValid
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
- corewrappers/Microsoft::WRL::Wrappers::HandleT::~HandleT
dev_langs:
- C++
helpviewer_keywords:
- Microsoft::WRL::Wrappers::HandleT class
- Microsoft::WRL::Wrappers::HandleT::Attach method
- Microsoft::WRL::Wrappers::HandleT::Close method
- Microsoft::WRL::Wrappers::HandleT::Detach method
- Microsoft::WRL::Wrappers::HandleT::Get method
- Microsoft::WRL::Wrappers::HandleT::handle_ data member
- Microsoft::WRL::Wrappers::HandleT::HandleT, constructor
- Microsoft::WRL::Wrappers::HandleT::InternalClose method
- Microsoft::WRL::Wrappers::HandleT::IsValid method
- Microsoft::WRL::Wrappers::HandleT::operator= operator
- Microsoft::WRL::Wrappers::HandleT::~HandleT, destructor
ms.assetid: 3822b32a-a426-4d94-a54d-919d4df60ee2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: ae6e7c1ec602cb57df071ecac24a0ac084331c3c
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/12/2018
ms.locfileid: "49162322"
---
# <a name="handlet-class"></a>HandleT クラス

オブジェクトへのハンドルを表します。

## <a name="syntax"></a>構文

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>パラメーター

*HandleTraits*<br/>
インスタンス、 [HandleTraits](../windows/handletraits-structure.md)ハンドルの一般的な特性を定義する構造体。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前     | 説明
-------- | -----------------------------
`Traits` | `HandleTraits` と同義。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                | 説明
----------------------------------- | --------------------------------------------------
[Handlet::handlet](#handlet)        | `HandleT` クラスの新しいインスタンスを初期化します。
[HandleT:: ~ HandleT](#tilde-handlet) | インスタンスを初期化解除、`HandleT`クラス。

### <a name="public-methods"></a>パブリック メソッド

名前                         | 説明
---------------------------- | ----------------------------------------------------------------------
[Handlet::attach](#attach)   | 現在の指定したハンドルに関連付けます`HandleT`オブジェクト。
[Handlet::close](#close)     | 現在の終了`HandleT`オブジェクト。
[Handlet::detach](#detach)   | 現在の関連付けを解除`HandleT`その基になるハンドルからオブジェクト。
[Handlet::get](#get)         | 基になるハンドルの値を取得します。
[Handlet::isvalid](#isvalid) | 示すかどうか、現在`HandleT`オブジェクト ハンドルを表します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                     | 説明
---------------------------------------- | ------------------------------------
[Handlet::internalclose](#internalclose) | 現在の終了`HandleT`オブジェクト。

### <a name="public-operators"></a>パブリック演算子

名前                                   | 説明
-------------------------------------- | ----------------------------------------------------------------------------------
[Handlet::operator =](#operator-assign) | 指定した値に移動`HandleT`現在オブジェクト`HandleT`オブジェクト。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------------------------------
[Handlet::handle _](#handle) | 表されるハンドルを含む、`HandleT`オブジェクト。

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers.h

**Namespace:** Microsoft::WRL::Wrappers

## <a name="tilde-handlet"></a>HandleT:: ~ HandleT

インスタンスを初期化解除、`HandleT`クラス。

```cpp
~HandleT();
```

## <a name="attach"></a>Handlet::attach

現在の指定したハンドルに関連付けます`HandleT`オブジェクト。

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドル。

## <a name="close"></a>Handlet::close

現在の終了`HandleT`オブジェクト。

```cpp
void Close();
```

### <a name="remarks"></a>Remarks

現在の基になるハンドル`HandleT`が閉じられると`HandleT`無効な状態に設定されています。

ハンドルが適切に終了しない場合は、呼び出し元のスレッドで例外が発生します。

## <a name="detach"></a>Handlet::detach

現在の関連付けを解除`HandleT`その基になるハンドルからオブジェクト。

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>戻り値

基になるハンドル。

### <a name="remarks"></a>Remarks

ときにこの操作が完了すると、現在`HandleT`が無効な状態に設定します。

## <a name="get"></a>Handlet::get

基になるハンドルの値を取得します。

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>戻り値

ハンドル。

## <a name="handle"></a>Handlet::handle _

表されるハンドルを含む、`HandleT`オブジェクト。

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlet"></a>Handlet::handlet

`HandleT` クラスの新しいインスタンスを初期化します。

```cpp
explicit HandleT(
   typename HandleTraits::Type h =
      HandleTraits::GetInvalidValue()  
);

HandleT(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドル。

### <a name="remarks"></a>Remarks

最初のコンス トラクターの初期化を`HandleT`オブジェクトへの有効なハンドルではないオブジェクトです。 2 番目のコンス トラクターを作成、新しい`HandleT`パラメーターからオブジェクト*h*します。

## <a name="internalclose"></a>Handlet::internalclose

現在の終了`HandleT`オブジェクト。

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>戻り値

**true**場合、現在`HandleT`正常。 それ以外の終了**false**します。

### <a name="remarks"></a>Remarks

`InternalClose()` は `protected` です。

## <a name="isvalid"></a>Handlet::isvalid

示すかどうか、現在`HandleT`オブジェクト ハンドルを表します。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

**true**場合、`HandleT`ハンドルを表します。 そうしないと、 **false**します。

## <a name="operator-assign"></a>Handlet::operator =

指定した値に移動`HandleT`現在オブジェクト`HandleT`オブジェクト。

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドルを右辺値の参照。

### <a name="return-value"></a>戻り値

現在への参照を`HandleT`オブジェクト。

### <a name="remarks"></a>Remarks

この操作を無効化、`HandleT`パラメーターで指定されたオブジェクト*h*します。
