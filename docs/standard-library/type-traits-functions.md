---
title: '&lt;type_traits&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- type_traits/std::is_assignable
- type_traits/std::is_copy_assignable
- type_traits/std::is_copy_constructible
- type_traits/std::is_default_constructible
- type_traits/std::is_move_assignable
- type_traits/std::is_move_constructible
- type_traits/std::is_nothrow_move_assignable
- type_traits/std::is_trivially_copy_assignable
- type_traits/std::is_trivially_move_assignable
- type_traits/std::is_trivially_move_constructible
ms.assetid: dce4492f-f3e4-4d5e-bdb4-5875321254ec
helpviewer_keywords:
- std::is_assignable
- std::is_copy_assignable
- std::is_copy_constructible
- std::is_default_constructible
- std::is_move_assignable
- std::is_move_constructible
- std::is_nothrow_move_assignable
- std::is_trivially_copy_assignable
- std::is_trivially_move_assignable
- std::is_trivially_move_constructible
ms.openlocfilehash: ff6d6066d90fe5049b89586ce657e62860c12f9f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt; 関数

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a>  is_assignable

`From` 型の値を `To` 型に代入できるかどうかをテストします。

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>パラメーター

オブジェクトの型には、割り当てを受け取る。

値を提供するオブジェクトの型。

### <a name="remarks"></a>コメント

評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 `From` と `To` の両方とも完全な型、`void`、または不明なバインドの配列にする必要があります。

## <a name="is_copy_assignable"></a>  is_copy_assignable

割り当て時に型をコピーできるかどうかをテストします。

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

### <a name="remarks"></a>コメント

型 `Ty` がコピー代入演算子を持つクラスの場合、型 predicate のインスタンスは true を保持します。それ以外の場合は false を保持します。 is_assignable\<Ty&, const Ty&> に相当します。

## <a name="is_copy_constructible"></a>  is_copy_constructible

型にコピー コンストラクターが存在するかどうかをテストします。

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

### <a name="remarks"></a>コメント

型 `Ty` がコピー コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

### <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

struct Copyable
{
    int val;
};

struct NotCopyable
{
   NotCopyable(const NotCopyable&) = delete;
   int val;

};

int main()
{
    std::cout << "is_copy_constructible<Copyable> == " << std::boolalpha
        << std::is_copy_constructible<Copyable>::value << std::endl;
    std::cout << "is_copy_constructible<NotCopyable> == " << std::boolalpha
        << std::is_copy_constructible<NotCopyable>::value << std::endl;

    return (0);
}

```

```Output
is_copy_constructible<Copyable> == true
is_copy_constructible<NotCopyable > == false
```

## <a name="is_default_constructible"></a>  is_default_constructible

型が既定のコンストラクターを持つかどうかをテストします。

```cpp
template <class Ty>
struct is_default_constructible;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

### <a name="remarks"></a>コメント

型 `T` が既定のコンストラクターを持つクラス型である場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。 これは、述語 `is_constructible<T>`と同じです。 型 `T` は完全な型、 `void`、または不明なバインドの配列である必要があります。

### <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

struct Simple
{
    Simple() : val(0) {}
    int val;
};

struct Simple2
{
    Simple2(int v) : val(v) {}
    int val;
};

int main()
{
    std::cout << "is_default_constructible<Simple> == " << std::boolalpha
        << std::is_default_constructible<Simple>::value << std::endl;
    std::cout << "is_default_constructible<Simple2> == " << std::boolalpha
        << std::is_default_constructible<Simple2>::value << std::endl;

    return (0);
}

```

```Output
is_default_constructible<Simple> == true
is_default_constructible<Simple2> == false
```

## <a name="is_move_assignable"></a>  is_move_assignable

型が移動代入可能であるかどうかをテストします。

```cpp
template <class T>
struct is_move_assignable;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

### <a name="remarks"></a>コメント

型への右辺値参照を型の参照に割り当てる事ができる場合、その型は移動代入可能です。 型述語は `is_assignable<T&, T&&>` と同じです。 移動代入できる型には、コンパイラにより生成された移動代入演算子またはユーザー定義の移動代入演算子を含む参照可能なスカラー型やクラス型があります。

## <a name="is_move_constructible"></a>  is_move_constructible

型に移動コンストラクターが存在するかどうかをテストします。

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

T 型に評価されます。

### <a name="remarks"></a>コメント

型 `T` が移動操作によって構築できる場合に、true と評価される型述語です。 この述語は `is_constructible<T, T&&>` と同じです。

## <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable

型が **nothrow** ムーブ代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

### <a name="remarks"></a>コメント

型 `Ty` が nothrow ムーブ代入演算子を持つ場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

## <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable

型が自明なコピー代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>パラメーター

`T` 照会する型。

### <a name="remarks"></a>コメント

型 `T` が自明なコピー代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。

クラス `T` の代入コンストラクターが自明となるのは、暗黙的に指定されている場合、クラス `T` に仮想関数がない場合、クラス `T` に仮想基底がない場合、クラス型の非静的データ メンバーすべてのクラスに自明な代入演算子が含まれており、かつクラスの型配列の非静的データ メンバーすべてでクラスに自明な代入演算子が含まれている場合です。

## <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable

型が自明なムーブ代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

### <a name="remarks"></a>コメント

型 `Ty` が自明なムーブ代入演算子を持つクラスの場合、型述語のインスタンスは true を保持します。それ以外の場合は false を保持します。

次の条件が満たされる場合、クラス `Ty` のムーブ代入演算子は自明です。

暗黙的に指定されている

クラス `Ty` に仮想関数がない

クラス `Ty` に仮想基底がない

クラス型のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

クラスの型配列のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

## <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible

型に自明な移動コンストラクターが存在するかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

### <a name="remarks"></a>コメント

型 `Ty` が自明な移動コンストラクターを持つクラスである場合、型述語のインスタンスは true を保持します。それ以外の場合は、false を保持します。

クラス `Ty` の移動コンストラクターが自明であるのは、以下の場合です。

暗黙的に宣言されている

そのパラメーターの型が暗黙的な宣言のものと同じである

クラス `Ty` に仮想関数がない

クラス `Ty` に仮想基底がない

クラスに揮発性の非静的データ メンバーがない

クラス `Ty` のすべての直接基本に自明な移動コンストラクターがある

クラス型のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

クラスの型配列のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
