---
description: '詳細情報: Platform:: Box クラス'
title: Platform::Box クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: cbfe8ec70f2ef4c58bf2c9459f2d0c4722817810
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284058"
---
# <a name="platformbox-class"></a>Platform::Box クラス

などの値型、 `Windows::Foundation::DateTime` またはなどのスカラー型を **`int`** 型に格納できるようにし `Platform::Object` ます。 通常は、 `Box` を明示的に使用する必要はありません。これは、値型を `Object^`にキャストすると、ボックス化が暗黙的に発生するためです。

### <a name="syntax"></a>構文

```cpp
ref class Box abstract;
```

### <a name="requirements"></a>必要条件

**ヘッダー:** vccorlib.h

**名前空間:** Platform

### <a name="members"></a>メンバー

|メンバー|説明|
|------------|-----------------|
|[ボックス](#ctor) | 指定された型の値をカプセル化する `Box` を作成します。 |
|[演算子ボックス &lt; Const T&gt;^](#box-const-t) | **`const`** 値クラスまたはクラスからへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。 |
|[演算子ボックス &lt; const Volatile T&gt;^](#box-const-volatile-t) | **`const volatile`** 値クラスまたは型からへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。 |
|[演算子ボックス &lt; T&gt;^](#box-t) | 値クラス `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[演算子ボックス &lt; Volatile T&gt;^](#box-volatile-t) | **`volatile`** 値クラスまたは型からへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。 |
|[Box:: operator T](#t) | 値クラスまたはクラスからへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。 |
|[Value プロパティ](#value) | `Box` オブジェクトにカプセル化された値を返します。 |

## <a name="boxbox-constructor"></a><a name="ctor"></a> Box:: Box コンストラクター

指定された型の値をカプセル化する `Box` を作成します。

### <a name="syntax"></a>構文

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>パラメーター

*Valu氏 g*<br/>
ボックス化する値の型 (、、、など **`int`** ) **`bool`** `float64` `DateTime` 。

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a> Box:: operator Box &lt; Const T &gt; ^ 演算子

**`const`** 値クラスまたはクラスからへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。

### <a name="syntax"></a>構文

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
値クラス、値構造体、または列挙型。 組み込み型が [既定の名前空間](../cppcx/default-namespace.md)に含まれています。

### <a name="return-value"></a>戻り値

`Platform::Box<T>^`Ref クラスのボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a> Box:: operator Box &lt; const Volatile T &gt; ^ 演算子

**`const volatile`** 値クラスまたは型からへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。

### <a name="syntax"></a>構文

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 組み込み型が [既定の名前空間](../cppcx/default-namespace.md)に含まれています。

### <a name="return-value"></a>戻り値

`Platform::Box<T>^`Ref クラスのボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a> Box:: operator Box &lt; T &gt; ^ 演算子

値クラス `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 組み込み型が [既定の名前空間](../cppcx/default-namespace.md)に含まれています。

### <a name="return-value"></a>戻り値

`Platform::Box<T>^`Ref クラスのボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a> Box:: operator Box &lt; Volatile T &gt; ^ 演算子

**`volatile`** 値クラスまたは型からへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。

### <a name="syntax"></a>構文

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 組み込み型が [既定の名前空間](../cppcx/default-namespace.md)に含まれています。

### <a name="return-value"></a>戻り値

`Platform::Box<T>^`Ref クラスのボックス化された元の値を表すインスタンス。

## <a name="boxoperator-t-operator"></a><a name="t"></a> Box:: operator T 演算子

値クラスまたはクラスからへのボックス化変換を有効に `T` **`enum`** `T` `Box<T>` します。

### <a name="syntax"></a>構文

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 組み込み型が [既定の名前空間](../cppcx/default-namespace.md)に含まれています。

### <a name="return-value"></a>戻り値

`Platform::Box<T>^`Ref クラスのボックス化された元の値を表すインスタンス。

## <a name="boxvalue-property"></a><a name="value"></a> Box:: Value プロパティ

`Box` オブジェクトにカプセル化された値を返します。

### <a name="syntax"></a>構文

```cpp
virtual property T Value{
   T get();
}
```

### <a name="return-value"></a>戻り値

値がボックス化される前と同じ型のボックス化された値を返します。

## <a name="see-also"></a>関連項目

[プラットフォーム名前空間](../cppcx/platform-namespace-c-cx.md)<br/>
[ボックス化](../cppcx/boxing-c-cx.md)
