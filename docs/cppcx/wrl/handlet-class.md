---
description: 詳細については、「クラスの使用」を参照してください。
title: HandleT クラス
ms.date: 10/03/2018
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
ms.openlocfilehash: 608433193729e3d9be5b9490c469bf0b04d3531c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250011"
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
ハンドルの共通特性を定義する [handletraits](handletraits-structure.md) 構造体のインスタンス。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前     | 説明
-------- | -----------------------------
`Traits` | `HandleTraits` と同義。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                | 説明
----------------------------------- | --------------------------------------------------
[ハンドラー Let:: ハンドラー Let](#handlet)        | `HandleT` クラスの新しいインスタンスを初期化します。
[ハンドラーの Let:: ~ の実行](#tilde-handlet) | クラスのインスタンスを初期化解除 `HandleT` します。

### <a name="public-methods"></a>パブリック メソッド

名前                         | 説明
---------------------------- | ----------------------------------------------------------------------
[実行の許可:: Attach](#attach)   | 指定したハンドルを現在の `HandleT` オブジェクトに関連付けます。
[実行の許可:: 閉じる](#close)     | 現在の `HandleT` オブジェクトを閉じます。
[使用方法::D etach](#detach)   | 基になるハンドルから現在のオブジェクトの関連付けを解除 `HandleT` します。
[Get-help Let:: Get](#get)         | 基になるハンドルの値を取得します。
[Let let:: IsValid](#isvalid) | 現在のオブジェクトがハンドルを表しているかどうかを示し `HandleT` ます。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                     | 説明
---------------------------------------- | ------------------------------------
[ハンドラー Let:: InternalClose](#internalclose) | 現在の `HandleT` オブジェクトを閉じます。

### <a name="public-operators"></a>パブリック演算子

名前                                   | 説明
-------------------------------------- | ----------------------------------------------------------------------------------
[Let let:: operator =](#operator-assign) | 指定したオブジェクトの値 `HandleT` を現在のオブジェクトに移動し `HandleT` ます。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------------------------------
[使用方法:: handle_](#handle) | オブジェクトによって表されるハンドルを格納し `HandleT` ます。

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

## <a name="requirements"></a>要件

**ヘッダー:** corewrappers .h

**名前空間:** Microsoft:: WRL:: Wrapper

## <a name="handlethandlet"></a><a name="tilde-handlet"></a> ハンドラーの Let:: ~ の実行

クラスのインスタンスを初期化解除 `HandleT` します。

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a> 実行の許可:: Attach

指定したハンドルを現在の `HandleT` オブジェクトに関連付けます。

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドル。

## <a name="handletclose"></a><a name="close"></a> 実行の許可:: 閉じる

現在の `HandleT` オブジェクトを閉じます。

```cpp
void Close();
```

### <a name="remarks"></a>解説

現在のの基になるハンドル `HandleT` が閉じられ、 `HandleT` が無効な状態に設定されています。

ハンドルが正常に終了しない場合は、呼び出し元のスレッドで例外が発生します。

## <a name="handletdetach"></a><a name="detach"></a> 使用方法::D etach

基になるハンドルから現在のオブジェクトの関連付けを解除 `HandleT` します。

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>戻り値

基になるハンドル。

### <a name="remarks"></a>解説

この操作が完了すると、現在のは `HandleT` 無効な状態に設定されます。

## <a name="handletget"></a><a name="get"></a> Get-help Let:: Get

基になるハンドルの値を取得します。

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>戻り値

ハンドル。

## <a name="handlethandle_"></a><a name="handle"></a> 使用方法:: handle_

オブジェクトによって表されるハンドルを格納し `HandleT` ます。

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a> ハンドラー Let:: ハンドラー Let

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

### <a name="remarks"></a>解説

最初のコンストラクターは、 `HandleT` オブジェクトに対する有効なハンドルではないオブジェクトを初期化します。 2番目のコンストラクターは、 `HandleT` パラメーター *h* から新しいオブジェクトを作成します。

## <a name="handletinternalclose"></a><a name="internalclose"></a> ハンドラー Let:: InternalClose

現在の `HandleT` オブジェクトを閉じます。

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>戻り値

**`true`** 現在のが `HandleT` 正常に終了した場合は。それ以外の場合は **`false`** 。

### <a name="remarks"></a>解説

`InternalClose()` が **`protected`** です。

## <a name="handletisvalid"></a><a name="isvalid"></a> Let let:: IsValid

現在のオブジェクトがハンドルを表しているかどうかを示し `HandleT` ます。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

**`true`** が `HandleT` ハンドルを表す場合は。それ以外の場合は **`false`** 。

## <a name="handletoperator"></a><a name="operator-assign"></a> Let let:: operator =

指定したオブジェクトの値 `HandleT` を現在のオブジェクトに移動し `HandleT` ます。

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*h*<br/>
ハンドルへの右辺値参照。

### <a name="return-value"></a>戻り値

現在のオブジェクトへの参照 `HandleT` 。

### <a name="remarks"></a>解説

この操作では、 `HandleT` parameter *h* によって指定されたオブジェクトを無効にします。
