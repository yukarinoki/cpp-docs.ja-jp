---
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
ms.openlocfilehash: 7a061ede19c5c4c181b5fea912b9c6212c583267
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50543911"
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

*val*<br/>
new_val の値を受け取るオブジェクト。

*new_val*<br/>
値が val にコピーまたは移動されるオブジェクト。

### <a name="remarks"></a>Remarks

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
|*Type*|渡された値の型*Arg*、これはの型よりも異なる可能性があります*Arg*します。 通常、転送関数のテンプレート引数によって決まります。|
|*arg*|キャストする引数。|

### <a name="return-value"></a>戻り値

右辺値参照を返します*Arg*で値が渡された場合*Arg*を右辺値または右辺値への参照元が、それ以外*Arg*その型を変更することがなく。

### <a name="remarks"></a>Remarks

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

*Index*<br/>
指定した要素の 0 ベースのインデックス。

*T1*<br/>
1 番目の pair 要素の型。

*T2*<br/>
2 番目の pair 要素の型。

*プル要求*<br/>
選択する pair。

### <a name="remarks"></a>Remarks

各テンプレート関数は、 `pair` 引数の要素への参照を返します。

インデックス付きのオーバー ロードの場合の値*インデックス*は 0 を返し`pr.first`場合の値*インデックス*は、関数が返す 1 `pr.second`。 型 `RI` は、返される要素の型です。

インデックス パラメーターがないオーバーロードでは、返される要素は型の引数によって推測されます。 呼び出す`get<T>(Tuple)`場合、コンパイラ エラーが生成されます*pr*より T 型の 1 つの要素が含まれています

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

*Val1*<br/>
`pair` の最初の要素を初期化する値。

*Val2*<br/>
`pair` の 2 番目の要素を初期化する値。

### <a name="return-value"></a>戻り値

作成されたペア オブジェクト: `pair`< `T`, `U`>( `Val1`, `Val2`)

### <a name="remarks"></a>Remarks

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
|*Type*|渡された引数の型から推論される型*Arg*と共に、参照縮小規則。|
|*arg*|キャストする引数。 型*Arg* 、右辺値参照として指定するが、`move`も左辺値参照は、右辺値参照にバインドできるため、左辺値の引数を受け取ります。|

### <a name="return-value"></a>戻り値

型が参照型であるかどうかに関係なく、右辺値参照としての `Arg`。

### <a name="remarks"></a>Remarks

テンプレート引数*型*を明示的に指定するが、渡された値の型から推測ではありません*Arg*します。 型*型*参照縮小規則に従ってさらに調整されます。

`move` は引数を移動しません。 無条件に引数をキャストするには、代わりに、-、左辺値可能性があります: で渡される値のコピーをするのではなく、コンパイラに移動して、その後、右辺値参照にできます*Arg*の型が移動を有効にした場合。 型の移動が有効ではない場合は、代わりにコピーされます。

値が渡された場合*Arg* lvalue です-は、名前またはそのアドレスを取得することができます:、移動が発生したときに無効にします。 渡された値を参照しない*Arg*名前またはアドレスが移動された後でします。

## <a name="swap"></a>  swap

2 つの [pair 構造体](../standard-library/pair-structure.md)オブジェクトの要素を交換します。

```cpp
template <class T, class U>
void swap(pair<T, U>& left, pair<T, U>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`pair` 型のオブジェクト。|
|*right*|`pair` 型のオブジェクト。|

### <a name="remarks"></a>Remarks

`swap` の利点の 1 つは、格納されるオブジェクトの型がコンパイラによって自動的に決定され、明示的に指定する必要がないことです。 `swap<int, int>(1, 2)` を使用する場合は、`swap` などの明示的なテンプレート引数を使用しないでください。これは、不必要に詳細になり、複雑な右辺値参照の問題が追加され、コンパイル エラーの原因となる可能性があるためです。

## <a name="see-also"></a>関連項目

[\<utility>](../standard-library/utility.md)<br/>
