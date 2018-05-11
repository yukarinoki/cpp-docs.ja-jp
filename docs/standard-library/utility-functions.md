---
title: '&lt;utility&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
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
ms.openlocfilehash: a26a4a0cab0bdea8a7a642cc760da0f3fc79b471
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="ltutilitygt-functions"></a>&lt;utility&gt; 関数

||||
|-|-|-|
|[exchange](#exchange)|[forward](#forward)|[get 関数 &lt;utility&gt;](#get)|
|[make_pair](#make_pair)|[move](#move)|[swap](#swap)|

## <a name="exchange"></a>  exchange

**(C++14)** オブジェクトに新しい値を代入し、古い値を返します。

```cpp
template <class T, class Other = T>
T exchange(T& val, Other&& new_val)
```

### <a name="parameters"></a>パラメーター

`val` New_val の値を受け取るオブジェクト。

`new_val` オブジェクトの値がコピーまたは val に移動します。

### <a name="remarks"></a>コメント

複合型の場合、`exchange` は、move コンストラクターが使用可能な場合に古い値がコピーされることを防ぎ、一時オブジェクトの場合や移動された場合は新しい値がコピーされることを防いで任意の型を新しい値として受け入れ、利用可能な任意の変換代入演算子を利用します。 左側の引数が右側に移動またはコピーされないという点で、exchange 関数は [std::swap](../standard-library/algorithm-functions.md#swap) と異なります。

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

## <a name="forward"></a>  forward

引数が右辺値または右辺値参照である場合に、条件付きで引数を右辺値参照にキャストします。 これによって、完全転送をサポートする転送関数に対する引数の右辺値性が復元されます。

```cpp
template <class Type>    // accepts lvalues
constexpr Type&& forward(typename remove_reference<Type>::type& Arg) noexcept

template <class Type>    // accepts everything else
constexpr Type&& forward(typename remove_reference<Type>::type&& Arg) noexcept
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Type`|`Arg` で渡される値の型は、`Arg` の型とは異なる場合があります。 通常、転送関数のテンプレート引数によって決まります。|
|`Arg`|キャストする引数。|

### <a name="return-value"></a>戻り値

`Arg` に渡された値が最初は右辺値または右辺値参照であった場合、`Arg` への右辺値参照を返します。それ以外の場合は、型を変更しないで `Arg` を返します。

### <a name="remarks"></a>コメント

`forward` を呼び出すために明示的なテンプレート引数を指定する必要があります。

`forward` は引数を転送しません。 代わりに、引数が元から右辺値または右辺値参照であった場合、条件付きで引数を右辺値参照にキャストすることにより、`forward` は、転送された引数の元の型の情報を使って、コンパイラでオーバーロードを解決できるようにします。 転送関数の引数の明確な型は元の型とは異なる場合があります。たとえば、右辺値が関数の引数として使用され、パラメーター名にバインドされている場合、名前を付けると、その値が実際に右辺値として存在するかどうかに関係なく左辺値になります。`forward` は引数の右辺値性を復元します。

オーバーロードの解決を実行するために引数の元の値の右辺値性を復元することは、*完全転送*と呼ばれます。 完全転送によって、テンプレート関数はいずれかの参照型の引数を受け取り、正しいオーバーロードの解決に必要な場合に引数の右辺値性を復元できます。 完全転送を使用することによって、右辺値の移動セマンティクスを保持することができ、引数の参照型のみが異なる関数にオーバーロードを用意する必要がなくなります。

## <a name="get"></a>  get

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

`Index` 指定した要素の 0 から始まるインデックス。

`T1` ペアの最初の要素の型。

`T2` 2 番目の pair 要素の型。

`pr` 選択する pair。

### <a name="remarks"></a>コメント

各テンプレート関数は、 `pair` 引数の要素への参照を返します。

インデックスを使用したオーバーロードでは、関数は、 `Index` の値が 0 の場合は `pr.first` を返し、 `Index` の値が 1 の場合は `pr.second`を返します。 型 `RI` は、返される要素の型です。

インデックス パラメーターがないオーバーロードでは、返される要素は型の引数によって推測されます。 `get<T>(Tuple)` に含まれる型 T の要素の数が 1 より多いか少ない場合、 `pr` を呼び出すと、コンパイラ エラーが生成されます。

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

    /*
    Output:
    9 3.14
    1 0.27
    */

}
```

## <a name="make_pair"></a>  make_pair

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

`Val1` 最初の要素を初期化する値`pair`です。

`Val2` 2 番目の要素を初期化する値`pair`です。

### <a name="return-value"></a>戻り値

作成されたペア オブジェクト: `pair`< `T`, `U`>( `Val1`, `Val2`)

### <a name="remarks"></a>コメント

`make_pair` は、[reference_wrapper Class](../standard-library/reference-wrapper-class.md) 型のオブジェクトを参照型に変換し、減衰配列および関数をポインターに変換します。

返された `pair` オブジェクトで、`T` は次のように決定されます。

- 入力の型 `T` が `reference_wrapper<X>` である場合、戻り値の型 `T` は `X&` です。

- それ以外の場合、戻り値の型 `T` は `decay<T>::type` になります。 [decay Class](../standard-library/decay-class.md) がサポートされない場合、戻り値の型 `T` は、入力の型 `T` と同じです。

戻り値の型 `U` は、入力の型 `U` から同様に決定されます。

`make_pair` の利点の 1 つは、格納されるオブジェクトの型がコンパイラによって自動的に決定され、明示的に指定する必要がないことです。 `make_pair<int, int>(1, 2)` を使用する場合は、`make_pair` などの明示的なテンプレート引数を使用しないでください。これは、不必要に詳細になり、複雑な右辺値参照の問題が追加され、コンパイル エラーの原因となる可能性があるためです。 この例の場合、正しい構文は `make_pair(1, 2)` です。

`make_pair` ヘルパー関数は、入力パラメーターとしてペアを必要とする関数に 2 個の値を渡すこともできます。

### <a name="example"></a>例

`make_pair` ヘルパー関数を使用してペアを宣言して初期化する方法の例については、「[pair 構造体](../standard-library/pair-structure.md)」を参照してください。

## <a name="move"></a>  move

無条件に引数を右辺値参照にキャストし、型の移動が有効である場合に型が移動できることを通知します。

```cpp
template <class Type>
constexpr typename remove_reference<Type>::type&& move(Type&& Arg) noexcept;
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`Type`|`Arg` で渡された引数の型と、参照縮小規則から推論される型。|
|`Arg`|キャストする引数。 `Arg` の型が右辺値参照として指定されているように見えますが、`move` では、左辺値参照を右辺値参照にバインドできるため、左辺値参照も受け取ります。|

### <a name="return-value"></a>戻り値

型が参照型であるかどうかに関係なく、右辺値参照としての `Arg`。

### <a name="remarks"></a>コメント

テンプレート引数 `Type` は明示的に指定されるものではなく、`Arg` で渡される値の型から推論されます。 `Type` の型は、参照縮小規則に従ってさらに調整されます。

`move` は引数を移動しません。 代わりに、その引数 (左辺値である可能性がある) を無条件に右辺値参照にキャストすることにより、型の移動が有効である場合、コンパイラは `Arg` に渡された値をコピーではなく移動できます。 型の移動が有効ではない場合は、代わりにコピーされます。

`Arg` で渡された値が左辺値である場合、つまり、名前を持つ場合や、そのアドレスを取得できる場合、移動が発生したときに無効になります。 移動した後、名前またはアドレスによって、`Arg` に渡された値を参照しないでください。

## <a name="swap"></a>  swap

2 つの [pair 構造体](../standard-library/pair-structure.md)オブジェクトの要素を交換します。

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|`left`|`pair` 型のオブジェクト。|
|`right`|`pair` 型のオブジェクト。|

### <a name="remarks"></a>コメント

`swap` の利点の 1 つは、格納されるオブジェクトの型がコンパイラによって自動的に決定され、明示的に指定する必要がないことです。 `swap<int, int>(1, 2)` を使用する場合は、`swap` などの明示的なテンプレート引数を使用しないでください。これは、不必要に詳細になり、複雑な右辺値参照の問題が追加され、コンパイル エラーの原因となる可能性があるためです。

## <a name="see-also"></a>関連項目

[\<utility>](../standard-library/utility.md)<br/>
