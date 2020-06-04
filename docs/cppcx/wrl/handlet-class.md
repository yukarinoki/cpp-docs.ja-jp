---
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
ms.openlocfilehash: bde7d7f1bd6730d96cb0f7a0d191a32eb8ed3e8c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371465"
---
# <a name="handlet-class"></a>HandleT クラス

オブジェクトへのハンドルを表します。

## <a name="syntax"></a>構文

```cpp
template <typename HandleTraits>
class HandleT;
```

### <a name="parameters"></a>パラメーター

*ハンドルトレイツ*<br/>
ハンドルの共通の特性を定義する[HandleTraits](handletraits-structure.md)構造体のインスタンス。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

名前     | 説明
-------- | -----------------------------
`Traits` | `HandleTraits` と同義。

### <a name="public-constructors"></a>パブリック コンストラクター

名前                                | 説明
----------------------------------- | --------------------------------------------------
[ハンドル::ハンドル](#handlet)        | `HandleT` クラスの新しいインスタンスを初期化します。
[ハンドル::~ハンドル](#tilde-handlet) | クラスのインスタンスを初期化解除します`HandleT`。

### <a name="public-methods"></a>パブリック メソッド

名前                         | 説明
---------------------------- | ----------------------------------------------------------------------
[ハンドル::アタッチ](#attach)   | 指定したハンドルを現在`HandleT`のオブジェクトに関連付けます。
[ハンドルT::閉じる](#close)     | 現在の `HandleT` オブジェクトを閉じます。
[ハンドルT::Dエタッハ](#detach)   | 現在`HandleT`のオブジェクトと基になるハンドルの関連付けを解除します。
[ハンドル::ゲット](#get)         | 基になるハンドルの値を取得します。
[ハンドル::イズバリ](#isvalid) | 現在`HandleT`のオブジェクトがハンドルを表すかどうかを示します。

### <a name="protected-methods"></a>プロテクト メソッド

名前                                     | 説明
---------------------------------------- | ------------------------------------
[ハンドル::内部閉じる](#internalclose) | 現在の `HandleT` オブジェクトを閉じます。

### <a name="public-operators"></a>パブリック演算子

名前                                   | 説明
-------------------------------------- | ----------------------------------------------------------------------------------
[ハンドルT::演算子=](#operator-assign) | 指定した`HandleT`オブジェクトの値を現在`HandleT`のオブジェクトに移動します。

### <a name="protected-data-members"></a>プロテクト データ メンバー

名前                        | 説明
--------------------------- | ----------------------------------------------------------------
[ハンドルT::handle_](#handle) | オブジェクトによって表されるハンドルを`HandleT`格納します。

## <a name="inheritance-hierarchy"></a>継承階層

`HandleT`

## <a name="requirements"></a>必要条件

**ヘッダー:** コアラッパー.h

**名前空間:** マイクロソフト::WRL::ラッパー

## <a name="handlethandlet"></a><a name="tilde-handlet"></a>ハンドル::~ハンドル

クラスのインスタンスを初期化解除します`HandleT`。

```cpp
~HandleT();
```

## <a name="handletattach"></a><a name="attach"></a>ハンドル::アタッチ

指定したハンドルを現在`HandleT`のオブジェクトに関連付けます。

```cpp
void Attach(
   typename HandleTraits::Type h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
ハンドル。

## <a name="handletclose"></a><a name="close"></a>ハンドルT::閉じる

現在の `HandleT` オブジェクトを閉じます。

```cpp
void Close();
```

### <a name="remarks"></a>解説

現在`HandleT`のハンドルの基になるハンドルは閉じられ、`HandleT`無効な状態に設定されます。

ハンドルが正しく閉じない場合は、呼び出し元のスレッドで例外が発生します。

## <a name="handletdetach"></a><a name="detach"></a>ハンドルT::Dエタッハ

現在`HandleT`のオブジェクトと基になるハンドルの関連付けを解除します。

```cpp
typename HandleTraits::Type Detach();
```

### <a name="return-value"></a>戻り値

基になるハンドル。

### <a name="remarks"></a>解説

この操作が完了すると、現在`HandleT`の状態は無効に設定されます。

## <a name="handletget"></a><a name="get"></a>ハンドル::ゲット

基になるハンドルの値を取得します。

```cpp
typename HandleTraits::Type Get() const;
```

### <a name="return-value"></a>戻り値

ハンドル。

## <a name="handlethandle_"></a><a name="handle"></a>ハンドルT::handle_

オブジェクトによって表されるハンドルを`HandleT`格納します。

```cpp
typename HandleTraits::Type handle_;
```

## <a name="handlethandlet"></a><a name="handlet"></a>ハンドル::ハンドル

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

*H*<br/>
ハンドル。

### <a name="remarks"></a>解説

最初のコンストラクターは、オブジェクト`HandleT`への有効なハンドルではないオブジェクトを初期化します。 2 番目のコンストラクターは`HandleT`、パラメーター *h*から新しいオブジェクトを作成します。

## <a name="handletinternalclose"></a><a name="internalclose"></a>ハンドル::内部閉じる

現在の `HandleT` オブジェクトを閉じます。

```cpp
virtual bool InternalClose();
```

### <a name="return-value"></a>戻り値

現在`HandleT`のクローズが正常に終了した場合は**true。** それ以外の場合**は false。**

### <a name="remarks"></a>解説

`InternalClose()` は `protected` です。

## <a name="handletisvalid"></a><a name="isvalid"></a>ハンドル::イズバリ

現在`HandleT`のオブジェクトがハンドルを表すかどうかを示します。

```cpp
bool IsValid() const;
```

### <a name="return-value"></a>戻り値

**が**ハンドルを`HandleT`表す場合は true、または a を表す場合は true。それ以外の場合**は false。**

## <a name="handletoperator"></a><a name="operator-assign"></a>ハンドルT::演算子=

指定した`HandleT`オブジェクトの値を現在`HandleT`のオブジェクトに移動します。

```cpp
HandleT& operator=(
   _Inout_ HandleT&& h
);
```

### <a name="parameters"></a>パラメーター

*H*<br/>
ハンドルへの右辺値参照。

### <a name="return-value"></a>戻り値

現在`HandleT`のオブジェクトへの参照。

### <a name="remarks"></a>解説

この操作は、パラメータ`HandleT`*h*で指定されたオブジェクトを無効にします。
