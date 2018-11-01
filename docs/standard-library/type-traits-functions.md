---
title: '&lt;type_traits&gt; 関数'
ms.date: 11/04/2016
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
ms.openlocfilehash: 05e72f07117cd5317dd0b8ea3590be9e87ae7b6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50653629"
---
# <a name="lttypetraitsgt-functions"></a>&lt;type_traits&gt; 関数

||||
|-|-|-|
|[is_assignable](#is_assignable)|[is_copy_assignable](#is_copy_assignable)|[is_copy_constructible](#is_copy_constructible)|
|[is_default_constructible](#is_default_constructible)|[is_move_assignable](#is_move_assignable)|[is_move_constructible](#is_move_constructible)|
|[is_nothrow_move_assignable](#is_nothrow_move_assignable)|[is_trivially_copy_assignable](#is_trivially_copy_assignable)|[is_trivially_move_assignable](#is_trivially_move_assignable)|
|[is_trivially_move_constructible](#is_trivially_move_constructible)|

## <a name="is_assignable"></a>  is_assignable

値かどうかをテスト*から*型に割り当てることができます、*に*型。

```cpp
template <class To, class From>
struct is_assignable;
```

### <a name="parameters"></a>パラメーター

*目的*<br/>
代入を受け取るオブジェクトの型。

*From*<br/>
値を渡すオブジェクトの型。

### <a name="remarks"></a>Remarks

評価されていない式 `declval<To>() = declval<From>()` は整形式である必要があります。 両方*から*と*に*完全な型は、必要があります**void**、または不明なバインドの配列。

## <a name="is_copy_assignable"></a>  is_copy_assignable

割り当て時に型をコピーできるかどうかをテストします。

```cpp
template <class Ty>
struct is_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*はコピー代入演算子を持つ、それ以外の場合は false を保持するクラスです。 is_assignable\<Ty&, const Ty&> に相当します。

## <a name="is_copy_constructible"></a>  is_copy_constructible

型にコピー コンストラクターが存在するかどうかをテストします。

```cpp
template <class Ty>
struct is_copy_constructible;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*はコピー コンス トラクターを持つ、それ以外の場合は false を保持するクラスです。

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

*T*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*既定コンス トラクターを持つ、それ以外の場合は false を保持するクラス型です。 これは、述語 `is_constructible<T>`と同じです。 型*T*完全な型である必要があります**void**、または不明なバインドの配列。

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

*T*<br/>
照会する型。

### <a name="remarks"></a>Remarks

型への右辺値参照を型の参照に割り当てる事ができる場合、その型は移動代入可能です。 型述語は `is_assignable<T&, T&&>` と同じです。 移動代入できる型には、コンパイラにより生成された移動代入演算子またはユーザー定義の移動代入演算子を含む参照可能なスカラー型やクラス型があります。

## <a name="is_move_constructible"></a>  is_move_constructible

型に移動コンストラクターが存在するかどうかをテストします。

```cpp
template <class T>
struct is_move_constructible;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
評価される型

### <a name="remarks"></a>Remarks

型の場合に true に評価される型の述語*T*移動操作を使用して構築できます。 この述語は `is_constructible<T, T&&>` と同じです。

## <a name="is_nothrow_move_assignable"></a>  is_nothrow_move_assignable

型が **nothrow** ムーブ代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_nothrow_move_assignable;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*が nothrow 移動代入演算子をそれ以外の場合は false を保持します。

## <a name="is_trivially_copy_assignable"></a>  is_trivially_copy_assignable

型が自明なコピー代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_copy_assignable;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*T*は自明なコピー代入演算子を持つ、それ以外の場合は false を保持するクラスです。

クラスの代入コンス トラクター *T*は暗黙的に入力すると、クラスに自明*T*仮想関数、クラスを持たない*T*のクラスの仮想基底がないです。クラス型のすべての非静的データ メンバーが自明な代入演算子、ありのクラスの型配列のすべての非静的データ メンバーのクラスが自明な代入演算子があります。

## <a name="is_trivially_move_assignable"></a>  is_trivially_move_assignable

型が自明なムーブ代入演算子を持つかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_move_assignable;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は自明なムーブ代入演算子を持つ、それ以外の場合は false を保持するクラスです。

クラスの移動代入演算子*Ty*は簡単では場合。

暗黙的に指定されている

クラスは、 *Ty*仮想関数がありません

クラスは、 *Ty*仮想基底クラスがありません

クラス型のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

クラスの型配列のすべての非静的データ メンバーのクラスに自明なムーブ代入演算子がある

## <a name="is_trivially_move_constructible"></a>  is_trivially_move_constructible

型に自明な移動コンストラクターが存在するかどうかをテストします。

```cpp
template <class Ty>
struct is_trivially_move_constructible;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

### <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は自明な移動コンス トラクターを持つ、それ以外の場合は false を保持するクラスです。

クラスの移動コンス トラクター *Ty*は簡単では場合。

暗黙的に宣言されている

そのパラメーターの型が暗黙的な宣言のものと同じである

クラスは、 *Ty*仮想関数がありません

クラスは、 *Ty*仮想基底クラスがありません

クラスに揮発性の非静的データ メンバーがない

すべての直接の基底クラスの*Ty*自明な移動コンス トラクターがあります。

クラス型のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

クラスの型配列のすべての非静的データ メンバーのクラスに自明な移動コンストラクターがある

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
