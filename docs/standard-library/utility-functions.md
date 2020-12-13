---
description: '詳細情報: &lt; ユーティリティ &gt; 関数'
title: '&lt;utility&gt; 関数'
ms.date: 11/04/2016
f1_keywords:
- utility/std::exchange
- utility/std::forward
- utility/std::make_pair
- utility/std::move
- utility/std::swap
ms.assetid: b1df38cd-3a59-4098-9c81-83342eb719a4
helpviewer_keywords:
- std::exchange [C++]
- std::forward [C++]
- std::make_pair [C++]
- std::move [C++]
- std::swap [C++]
ms.openlocfilehash: 421f9a24d59d25e03f5b947c2c68cbecb4a71b3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153474"
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt; 関数

## <a name="as_const"></a><a name="asconst"></a> as_const

```cpp
template <class T> constexpr add_const_t<T>& as_const(T& t) noexcept;
template <class T> void as_const(const T&&) = delete;
```

### <a name="return-value"></a>戻り値

*T* を返します。

## <a name="declval"></a><a name="declval"></a> declval

```cpp
template <class T> add_rvalue_reference_t<T> declval() noexcept;  // as unevaluated operand
```

## <a name="exchange"></a><a name="exchange"></a> エクスチェンジ

**(C++14)** オブジェクトに新しい値を代入し、古い値を返します。

```cpp
template <class T, class Other = T>
    T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>パラメーター

*val*\
new_val の値を受け取るオブジェクト。

*new_val*\
値が val にコピーまたは移動されるオブジェクト。

### <a name="remarks"></a>解説

複合型の場合、`exchange` は、move コンストラクターが使用可能な場合に古い値がコピーされることを防ぎ、一時オブジェクトの場合や移動された場合は新しい値がコピーされることを防いで任意の型を新しい値として受け入れ、利用可能な任意の変換代入演算子を利用します。 左の引数が右の引数に移動またはコピーされない場合、exchange 関数は [std:: swap](../standard-library/algorithm-functions.md#swap) とは異なります。

### <a name="example"></a>例

次の例は、`exchange` を使用する方法を示しています。 実際には、`exchange` はコピーすると負荷がかかる大きなオブジェクトでの利用に最も適しています。

```cpp
#include <utility>
#include <iostream>

using namespace std;

struct C
{
   int i;
   //...
};

int main()
{
   // Use brace initialization
   C c1{ 1 };
   C c2{ 2 };
   C result = exchange(c1, c2);
   cout << "The old value of c1 is: " << result.i << endl;
   cout << "The new value of c1 after exchange is: " << c1.i << endl;

   return 0;
}
```

```Output
The old value of c1 is: 1
The new value of c1 after exchange is: 2
```

## <a name="forward"></a><a name="forward"></a> 推進

引数が右辺値または右辺値参照である場合に、条件付きで引数を右辺値参照にキャストします。 これによって、完全転送をサポートする転送関数に対する引数の右辺値性が復元されます。

```cpp
template <class Type>    // accepts lvalues
    constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
    constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>パラメーター

*各種*\
*Arg で渡* される値の型。 *arg* の型とは異なる場合があります。 通常、転送関数のテンプレート引数によって決まります。

*Arg*\
キャストする引数。

### <a name="return-value"></a>戻り値

*Arg* で渡された値が最初は右辺値または右辺値参照であった場合、 *arg* への右辺値参照を返します。それ以外の場合は、型を変更せずに *Arg* を返します。

### <a name="remarks"></a>解説

`forward` を呼び出すために明示的なテンプレート引数を指定する必要があります。

`forward` は引数を転送しません。 代わりに、引数が元から右辺値または右辺値参照であった場合、条件付きで引数を右辺値参照にキャストすることにより、`forward` は、転送された引数の元の型の情報を使って、コンパイラでオーバーロードを解決できるようにします。 転送関数に対する引数の見かけ上の型は、元の型とは異なる場合があります。たとえば、右辺値が関数の引数として使用され、パラメーター名にバインドされている場合などです。名前を指定すると、実際に右辺値として存在する任意の値を使用して、その `forward` 引数の右辺値性が復元されます。

オーバーロードの解決を行うために、引数の元の値の右辺値性を復元することを、 *完全転送* と呼びます。 完全転送によって、テンプレート関数はいずれかの参照型の引数を受け取り、正しいオーバーロードの解決に必要な場合に引数の右辺値性を復元できます。 完全転送を使用することによって、右辺値の移動セマンティクスを保持することができ、引数の参照型のみが異なる関数にオーバーロードを用意する必要がなくなります。

## <a name="from_chars"></a><a name="from_chars"></a> from_chars

```cpp
from_chars_result from_chars(const char* first, const char* last, see below& value, int base = 10);

from_chars_result from_chars(const char* first, const char* last, float& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, double& value, chars_format fmt = chars_format::general);

from_chars_result from_chars(const char* first, const char* last, long double& value, chars_format fmt = chars_format::general);
```

## <a name="get"></a><a name="get"></a> 取得

`pair` オブジェクトから、インデックスの位置または型を使用して要素を取得します。

```cpp
// get reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&
    get(pair<T1, T2>& Pr) noexcept;

// get reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1& get(pair<T1, T2>& Pr) noexcept;

// get reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2& get(pair<T1, T2>& Pr) noexcept;

// get const reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr const tuple_element_t<Index, pair<T1, T2>>&
    get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr const T1& get(const pair<T1, T2>& Pr) noexcept;

// get const reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr const T2& get(const pair<T1, T2>& Pr) noexcept;

// get rvalue reference to element at Index in pair Pr
template <size_t Index, class T1, class T2>
    constexpr tuple_element_t<Index, pair<T1, T2>>&&
    get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T1 in pair Pr
template <class T1, class T2>
    constexpr T1&& get(pair<T1, T2>&& Pr) noexcept;

// get rvalue reference to element T2 in pair Pr
template <class T2, class T1>
    constexpr T2&& get(pair<T1, T2>&& Pr) noexcept;
```

### <a name="parameters"></a>パラメーター

*[インデックス]* \
選択された要素の0から始まるインデックス。

*T1*\
1 番目の pair 要素の型。

*T2*\
2 番目の pair 要素の型。

*pr*\
選択する pair。

### <a name="remarks"></a>解説

各テンプレート関数は、 `pair` 引数の要素への参照を返します。

インデックス付きオーバーロードの場合、 *index* の値が0の場合、関数は `pr.first` を返します。 *インデックス* の値が1の場合、関数はを返し `pr.second` ます。 型 `RI` は、返される要素の型です。

インデックスパラメーターがないオーバーロードの場合、返される要素は型引数によって推測されます。 `get<T>(Tuple)` *Pr* に T 型の要素が複数含まれている場合、を呼び出すとコンパイラエラーが発生します。

### <a name="example"></a>例

```cpp
#include <utility>
#include <iostream>
using namespace std;
int main()
{

    typedef pair<int, double> MyPair;

    MyPair c0(9, 3.14);

    // get elements by index
    cout << " " << get<0>(c0);
    cout << " " << get<1>(c0) << endl;

    // get elements by type (C++14)
    MyPair c1(1, 0.27);
    cout << " " << get<int>(c1);
    cout << " " << get<double>(c1) << endl;
}
```

```Output
9 3.14
1 0.27
```

## <a name="index_sequence"></a><a name="index_sequence"></a> index_sequence

```cpp
template<size_t... I>
    using index_sequence = integer_sequence<size_t, I...>;
```

## <a name="index_sequence_for"></a><a name="index_sequence_for"></a> index_sequence_for

```cpp
template<class... T>
    using index_sequence_for = make_index_sequence<sizeof...(T)>;
```

## <a name="make_index_sequence"></a><a name="make_index_sequence"></a> make_index_sequence

```cpp
template<size_t N>
    using make_index_sequence = make_integer_sequence<size_t, N>;
```

## <a name="make_integer_sequence"></a><a name="make_integer_sequence"></a> make_integer_sequence

```cpp
template<class T, T N>
    using make_integer_sequence = integer_sequence<T, see below >;
```

## <a name="make_pair"></a><a name="make_pair"></a> make_pair

`pair` 型のオブジェクトを作成するために使用できるテンプレート関数。コンポーネントの型は、パラメーターとして渡されるデータ型に基づいて自動的に選択されます。

```cpp
template <class T, class U>
    pair<T, U> make_pair(T& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T& Val1, U&& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U& Val2);

template <class T, class U>
    pair<T, U> make_pair(T&& Val1, U&& Val2);
```

### <a name="parameters"></a>パラメーター

*Val1*\
`pair` の最初の要素を初期化する値。

*Val2*\
`pair` の 2 番目の要素を初期化する値。

### <a name="return-value"></a>戻り値

構築されたペアオブジェクト: `pair` < `T` 、 `U`> ( `Val1` 、 `Val2` )。

### <a name="remarks"></a>解説

`make_pair` は、[reference_wrapper Class](../standard-library/reference-wrapper-class.md) 型のオブジェクトを参照型に変換し、減衰配列および関数をポインターに変換します。

返された `pair` オブジェクトで、`T` は次のように決定されます。

- 入力の型 `T` が `reference_wrapper<X>` である場合、戻り値の型 `T` は `X&` です。

- それ以外の場合、戻り値の型 `T` は `decay<T>::type` になります。 [ディケイ Class](../standard-library/decay-class.md)がサポートされていない場合、戻り値の型 `T` は入力型と同じに `T` なります。

戻り値の型 `U` は、入力の型 `U` から同様に決定されます。

の利点の1つは、格納される `make_pair` オブジェクトの型がコンパイラによって自動的に決定され、明示的に指定する必要がないことです。 を使用する場合は、のような明示的なテンプレート引数を使用しない `make_pair<int, int>(1, 2)` `make_pair` でください。これは詳細なので、コンパイルエラーを引き起こす可能性がある複雑な右辺値参照の問題が追加されます。 この例の場合、正しい構文は `make_pair(1, 2)` です。

`make_pair` ヘルパー関数は、入力パラメーターとしてペアを必要とする関数に 2 個の値を渡すこともできます。

### <a name="example"></a>例

`make_pair` ヘルパー関数を使用してペアを宣言して初期化する方法の例については、「[pair 構造体](../standard-library/pair-structure.md)」を参照してください。

## <a name="move"></a><a name="move"></a> 合わせ

無条件に引数を右辺値参照にキャストし、型の移動が有効である場合に型が移動できることを通知します。

```cpp
template <class Type>
    constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>パラメーター

*各種*\
*Arg* で渡された引数の型から推測される型と、参照の折りたたみ規則が含まれます。

*Arg*\
キャストする引数。 *Arg* の型は右辺値参照として指定されているように見えますが、左辺値参照を右辺値参照にバインドできるので、左辺値の `move` 引数も受け入れます。

### <a name="return-value"></a>戻り値

型が参照型であるかどうかに関係なく、右辺値参照としての `Arg`。

### <a name="remarks"></a>解説

テンプレート引数の *型* は明示的に指定することを意図していませんが、 *Arg* で渡される値の型から推測されます。 *型* の型は、参照の折りたたみ規則に従ってさらに調整されます。

`move` は引数を移動しません。 代わりに、その引数 (左辺値である可能性があります) を無条件に右辺値参照にキャストすることにより、コンパイラは、型が移動が有効な場合に、 *Arg* で渡される値をコピーではなく移動できます。 型が移動可能でない場合は、代わりにコピーされます。

*Arg* で渡される値が左辺値である場合 (つまり、名前またはそのアドレスを取得できる場合)、移動が発生すると無効になります。 *引数* に渡された値を、移動後の名前またはアドレスで参照しないでください。

## <a name="move_if_noexcept"></a><a name="moveif"></a> move_if_noexcept

```cpp
template <class T> constexpr conditional_t< !is_nothrow_move_constructible_v<T> && is_copy_constructible_v<T>, const T&, T&&> move_if_noexcept(T& x) noexcept;
```

## <a name="swap"></a><a name="swap"></a> フォト

2つの型または [ペアの構造体](../standard-library/pair-structure.md) オブジェクトの要素を交換します。

```cpp
template <class T>
    void swap(T& left, T& right) noexcept(see below );
template <class T, size_t N>
    void swap(T (&left)[N], T (&right)[N]) noexcept(is_nothrow_swappable_v<T>);
template <class T, class U>
    void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

*左側*\
型または型のオブジェクト `pair` 。

*そうです*\
型または型のオブジェクト `pair` 。

### <a name="remarks"></a>解説

の利点の1つは、格納される `swap` オブジェクトの型がコンパイラによって自動的に決定され、明示的に指定する必要がないことです。 を使用する場合は、のような明示的なテンプレート引数を使用しない `swap<int, int>(1, 2)` `swap` でください。これは詳細なので、コンパイルエラーを引き起こす可能性がある複雑な右辺値参照の問題が追加されます。

## <a name="to_chars"></a><a name="to_chars"></a> to_chars

```cpp
to_chars_result to_chars(char* first, char* last, see below value, int base = 10);
to_chars_result to_chars(char* first, char* last, float value);
to_chars_result to_chars(char* first, char* last, double value);
to_chars_result to_chars(char* first, char* last, long double value);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt);
to_chars_result to_chars(char* first, char* last, float value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, double value, chars_format fmt, int precision);
to_chars_result to_chars(char* first, char* last, long double value, chars_format fmt, int precision);
```

### <a name="remarks"></a>解説

範囲を埋めることによって値を文字列に変換し `[first, last)` ます。ここで、 `[first, last)` は有効な範囲である必要があります。
