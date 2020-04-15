---
title: Platform::Box クラス
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Box
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
ms.openlocfilehash: 7484bcda3f05a8a9e56a33222d0630d4597e1219
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81354756"
---
# <a name="platformbox-class"></a>Platform::Box クラス

`Windows::Foundation::DateTime` などの値型または `int` などのスカラー型を `Platform::Object` 型に格納できるようにします。 通常は、 `Box` を明示的に使用する必要はありません。これは、値型を `Object^`にキャストすると、ボックス化が暗黙的に発生するためです。

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
|[演算子&lt;ボックス const T&gt;^](#box-const-t) | `const` 値クラスの `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[オペレータ&lt;ボックス コンスト 揮発性 T&gt;^](#box-const-volatile-t) | `const volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[オペレーター&lt;ボックス T&gt;^](#box-t) | 値クラス `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[オペレータ&lt;ボックス揮発性 T&gt;^](#box-volatile-t) | `volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[ボックス::演算子T](#t) | 値クラス `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。 |
|[値プロパティ](#value) | `Box` オブジェクトにカプセル化された値を返します。 |

## <a name="boxbox-constructor"></a><a name="ctor"></a>ボックス::ボックスコンストラクタ

指定された型の値をカプセル化する `Box` を作成します。

### <a name="syntax"></a>構文

```cpp
Box(T valueArg);
```

### <a name="parameters"></a>パラメーター

*値Arg*<br/>
ボックス化される値の型 (たとえば、`int`、`bool`、`float64`、`DateTime`。)

## <a name="boxoperator-boxltconst-tgt-operator"></a><a name="box-const-t"></a>ボックス::演算子ボックス&lt;定数&gt;T ^ 演算子

`const` 値クラスの `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
値クラス、値構造体、または列挙型。 [既定の名前空間](../cppcx/default-namespace.md)に組み込みの型を含めます。

### <a name="return-value"></a>戻り値

ref`Platform::Box<T>^`クラスにボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxltconst-volatile-tgt-operator"></a><a name="box-const-volatile-t"></a>ボックス::演算子ボックス&lt;定数揮発性T&gt;^ 演算子

`const volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<const volatile T>^(const volatile T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 [既定の名前空間](../cppcx/default-namespace.md)に組み込みの型を含めます。

### <a name="return-value"></a>戻り値

ref`Platform::Box<T>^`クラスにボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxlttgt-operator"></a><a name="box-t"></a>ボックス::演算子ボックス&lt;&gt;T ^ 演算子

値クラス `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<const T>^(const T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 [既定の名前空間](../cppcx/default-namespace.md)に組み込みの型を含めます。

### <a name="return-value"></a>戻り値

ref`Platform::Box<T>^`クラスにボックス化された元の値を表すインスタンス。

## <a name="boxoperator-boxltvolatile-tgt-operator"></a><a name="box-volatile-t"></a>ボックス::演算子ボックス&lt;揮発性T&gt;^ 演算子

`volatile` 値クラスの `T` または `enum` 型の `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<volatile T>^(volatile T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 [既定の名前空間](../cppcx/default-namespace.md)に組み込みの型を含めます。

### <a name="return-value"></a>戻り値

ref`Platform::Box<T>^`クラスにボックス化された元の値を表すインスタンス。

## <a name="boxoperator-t-operator"></a><a name="t"></a>ボックス::演算子 T 演算子

値クラス `T` または `enum` クラスの `T` から `Box<T>` へのボックス化変換を有効にします。

### <a name="syntax"></a>構文

```cpp
operator Box<T>^(T valueType);
```

### <a name="parameters"></a>パラメーター

*T*<br/>
列挙型、値クラス、または値構造体。 [既定の名前空間](../cppcx/default-namespace.md)に組み込みの型を含めます。

### <a name="return-value"></a>戻り値

ref`Platform::Box<T>^`クラスにボックス化された元の値を表すインスタンス。

## <a name="boxvalue-property"></a><a name="value"></a>ボックス::値プロパティ

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
