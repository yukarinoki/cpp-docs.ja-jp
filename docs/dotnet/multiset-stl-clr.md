---
title: multiset (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::multiset
- cliext::multiset::begin
- cliext::multiset::clear
- cliext::multiset::const_iterator
- cliext::multiset::const_reference
- cliext::multiset::const_reverse_iterator
- cliext::multiset::count
- cliext::multiset::difference_type
- cliext::multiset::empty
- cliext::multiset::end
- cliext::multiset::equal_range
- cliext::multiset::erase
- cliext::multiset::find
- cliext::multiset::generic_container
- cliext::multiset::generic_iterator
- cliext::multiset::generic_reverse_iterator
- cliext::multiset::generic_value
- cliext::multiset::insert
- cliext::multiset::iterator
- cliext::multiset::key_comp
- cliext::multiset::key_compare
- cliext::multiset::key_type
- cliext::multiset::lower_bound
- cliext::multiset::make_value
- cliext::multiset::multiset
- cliext::multiset::operator=
- cliext::multiset::rbegin
- cliext::multiset::reference
- cliext::multiset::rend
- cliext::multiset::reverse_iterator
- cliext::multiset::size
- cliext::multiset::size_type
- cliext::multiset::swap
- cliext::multiset::to_array
- cliext::multiset::upper_bound
- cliext::multiset::value_comp
- cliext::multiset::value_compare
- cliext::multiset::value_type
- cliext::multiset::operator!=
- cliext::multiset::operator<
- cliext::multiset::operator<=
- cliext::multiset::operator==
- cliext::multiset::operator>
- cliext::multiset::operator>=
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- multiset class [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- count member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- equal_range member [STL/CLR]
- erase member [STL/CLR]
- find member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- key_comp member [STL/CLR]
- key_compare member [STL/CLR]
- key_type member [STL/CLR]
- lower_bound member [STL/CLR]
- make_value member [STL/CLR]
- map member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- operator member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: 7c46e2b4-cd88-49b7-a9e6-63ad5ae7feb5
ms.openlocfilehash: 811b96cca1fbf661def181d16dcb6a02c6c398d8
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208495"
---
# <a name="multiset-stlclr"></a>multiset (STL/CLR)

このテンプレートクラスは、双方向アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナー `multiset` を使用して、要素のシーケンスを (ほぼ) バランスのとれたノードのツリーとして管理します。各ノードには1つの要素が格納されます。

以下の説明では、`GValue` は `GKey`と同じですが、後者が ref 型である場合を除き、*キー*と同じです。この場合、`Key^`します。

## <a name="syntax"></a>構文

```cpp
template<typename Key>
    ref class multiset
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::ITree<Gkey, GValue>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*[キー]*<br/>
被制御シーケンス内の要素のキー コンポーネントの型。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<cliext/set >

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型定義|説明|
|---------------------|-----------------|
|[multiset::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[multiset::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[multiset::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[multiset::difference_type (STL/CLR)](#difference_type)|2つの要素間の (符号付きの) 距離の型。|
|[multiset::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリックインターフェイスの型。|
|[multiset::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリックインターフェイスの反復子の型。|
|[multiset::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリックインターフェイスの反転反復子の型。|
|[multiset::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリックインターフェイスの要素の型。|
|[multiset::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[multiset::key_compare (STL/CLR)](#key_compare)|2つのキーの順序付けデリゲート。|
|[multiset::key_type (STL/CLR)](#key_type)|順序付けキーの型です。|
|[multiset::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[multiset::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[multiset::size_type (STL/CLR)](#size_type)|2つの要素間の (負ではない) 距離の型。|
|[multiset::value_compare (STL/CLR)](#value_compare)|2つの要素の値の順序付けデリゲート。|
|[multiset::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[multiset::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[multiset::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[multiset::count (STL/CLR)](#count)|指定されたキーに一致する要素をカウントします。|
|[multiset::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[multiset::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[multiset::equal_range (STL/CLR)](#equal_range)|指定したキーに一致する範囲を検索します。|
|[multiset::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[multiset::find (STL/CLR)](#find)|指定したキーに一致する要素を検索します。|
|[multiset::insert (STL/CLR)](#insert)|要素を追加します。|
|[multiset::key_comp (STL/CLR)](#key_comp)|2つのキーの順序付けデリゲートをコピーします。|
|[multiset::lower_bound (STL/CLR)](#lower_bound)|指定されたキーに一致する範囲の先頭を検索します。|
|[multiset::make_value (STL/CLR)](#make_value)|値オブジェクトを構築します。|
|[multiset::multiset (STL/CLR)](#multiset)|コンテナー オブジェクトを構築します。|
|[multiset::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[multiset::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[multiset::size (STL/CLR)](#size)|要素の数をカウントします。|
|[multiset::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[multiset::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|
|[multiset::upper_bound (STL/CLR)](#upper_bound)|指定されたキーに一致する範囲の末尾を検索します。|
|[multiset::value_comp (STL/CLR)](#value_comp)|2つの要素の値の順序付けデリゲートをコピーします。|

|演算子|説明|
|--------------|-----------------|
|[multiset::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[operator!= (multiset) (STL/CLR)](#op_neq)|`multiset` オブジェクトが別の `multiset` オブジェクトと等しくないかどうかを判断します。|
|[operator< (multiset) (STL/CLR)](#op_lt)|`multiset` オブジェクトが、別の `multiset` オブジェクトより小さいかどうかを判断します。|
|[operator<= (multiset) (STL/CLR)](#op_lteq)|`multiset` オブジェクトが、別の `multiset` オブジェクト以下かどうかを判断します。|
|[operator== (multiset) (STL/CLR)](#op_eq)|`multiset` オブジェクトが別の `multiset` オブジェクトと等しいかどうかを判断します。|
|[operator> (multiset) (STL/CLR)](#op_gt)|`multiset` オブジェクトが、別の `multiset` オブジェクトより大きいかどうかを判断します。|
|[operator>= (multiset) (STL/CLR)](#op_gteq)|`multiset` オブジェクトが、別の `multiset` オブジェクト以上かどうかを判断します。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|<xref:System.Collections.IEnumerable>|要素を順番に処理します。|
|<xref:System.Collections.ICollection>|要素のグループを維持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番に処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|
|ITree キー、値 >\<|ジェネリックコンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、制御するシーケンスのストレージを個々のノードとして割り当て、解放します。 要素は、ノード間のリンクを変更することによって、ノード間のリンクを変更することによって順序を維持する、(ほぼ) 均衡ツリーに挿入されます。ノード間でのコンテンツのコピーは行われません。 つまり、要素を自由に挿入および削除できます。

オブジェクトは、[マルチセット:: key_compare (STL/CLR)](../dotnet/multiset-key-compare-stl-clr.md)型の格納されたデリゲートオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます。 マルチセットを作成するときに、格納されているデリゲートオブジェクトを指定できます。delegate オブジェクトを指定しない場合、既定では `operator<(key_type, key_type)`の比較が行われます。 この格納されているオブジェクトにアクセスするには、メンバー関数[マルチセット:: key_comp (STL/CLR)](../dotnet/multiset-key-comp-stl-clr.md)`()`を呼び出します。

このようなデリゲートオブジェクトは、[マルチセット:: key_type (STL/CLR)](../dotnet/multiset-key-type-stl-clr.md)型のキーに対して厳密弱順序を強制する必要があります。 つまり、`X` と `Y`の2つのキーについては、次のようになります。

`key_comp()(X, Y)` は、すべての呼び出しで同じブール値を返します。

`key_comp()(X, Y)` が true の場合、`key_comp()(Y, X)` は false である必要があります。

`key_comp()(X, Y)` が true の場合、`Y`前に `X` が順序付けられていると言います。

`!key_comp()(X, Y) && !key_comp()(Y, X)` が true の場合、`X` と `Y` は等価の順序付けと呼ばれます。

被制御シーケンスの `Y` の前にある要素 `X` の場合、`key_comp()(Y, X)` は false になります。 (既定のデリゲートオブジェクトの場合、キーの値が減少することはありません)。テンプレートクラス[セット (STL/CLR)](../dotnet/set-stl-clr.md)とは異なり、テンプレートクラス `multiset` のオブジェクトでは、すべての要素のキーが一意である必要はありません。 (2 つ以上のキーが同等の順序を持つことができます)。

各要素は、"値" と "値" の両方として機能します。 シーケンスは、シーケンス内の要素数の対数に比例した数の操作で、任意の要素の検索、挿入、および削除を許可する方法で表現されます (対数時間)。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。

マルチセットは双方向反復子をサポートします。つまり、被制御シーケンス内の要素を指定する反復子によって隣接する要素にステップインすることができます。 特殊なヘッドノードは、[マルチセット:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`によって返される反復子に対応します。 この反復子をデクリメントして、被制御シーケンスの最後の要素 (存在する場合) に移動することができます。 マルチセット反復子をインクリメントしてヘッドノードに移動すると、`end()`と等しいかどうかが比較されます。 ただし、`end()`によって返される反復子を逆参照することはできません。

ランダムアクセス反復子を必要とする数値の位置を指定することで、マルチセット要素を直接参照することはできないことに注意してください。

マルチセット反復子は、関連付けられたマルチセットノードへのハンドルを格納します。このノードは、関連付けられているコンテナーへのハンドルを格納します。 反復子は、関連付けられているコンテナーオブジェクトと共にのみ使用できます。 マルチセットの反復子は、関連付けられているマルチセットノードが一部のマルチセットに関連付けられている限り有効です。 さらに、有効な反復子は dereferencable です。これを使用すると、指定した要素の値にアクセスしたり変更したりすることができます。これは、`end()`と等しくない場合に限ります。

要素を消去または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナーを破棄すると、すべての要素が消去されます。 したがって、要素の型が ref クラスであるコンテナーは、コンテナーの直後要素が存在しないことを保証します。 ただし、ハンドルのコンテナーが要素を破棄し*ない*ことに注意してください。

## <a name="members"></a>メンバー

## <a name="multisetbegin-stlclr"></a><a name="begin"></a>マルチセット:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定する双方向反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_multiset_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mymultiset::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
```

## <a name="multisetclear-stlclr"></a><a name="clear"></a>マルチセット:: clear (STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

このメンバー関数は、[マルチセット](../dotnet/multiset-erase-stl-clr.md):: [begin](../dotnet/multiset-begin-stl-clr.md) (stl/clr)`(``(),` マルチセット:: [end](../dotnet/multiset-end-stl-clr.md) (stl/clr)`())`を効果的に呼び出します。 このメソッドを使用して、被制御シーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_multiset_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 0
a b
size() = 0
```

## <a name="multisetconst_iterator-stlclr"></a><a name="const_iterator"></a>マルチセット:: const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数双方向反復子として使用できる、未指定の型 `T2` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Mymultiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetconst_reference-stlclr"></a><a name="const_reference"></a>マルチセット:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Mymultiset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Mymultiset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>マルチセット:: const_reverse_iterator (STL/CLR)

被制御シーケンスの定数反転反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数反転反復子として使用できる、指定されていない型 `T4` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Mymultiset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="multisetcount-stlclr"></a><a name="count"></a>マルチセット:: count (STL/CLR)

指定したキーに一致する要素の数を検索します。

### <a name="syntax"></a>構文

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*と同じ順序付けを持つ被制御シーケンス内の要素の数を返します。 被制御シーケンス内の指定したキーに一致する現在の要素の数を確認する場合に、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_multiset_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("count(L'A') = {0}", c1.count(L'A'));
    System::Console::WriteLine("count(L'b') = {0}", c1.count(L'b'));
    System::Console::WriteLine("count(L'C') = {0}", c1.count(L'C'));
    return (0);
    }
```

```Output
a b c
count(L'A') = 0
count(L'b') = 1
count(L'C') = 0
```

## <a name="multisetdifference_type-stlclr"></a><a name="difference_type"></a>マルチセット::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_multiset_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mymultiset::difference_type diff = 0;
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (Mymultiset::iterator it = c1.end(); it != c1.begin(); --it)
        --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="multisetempty-stlclr"></a><a name="empty"></a>マルチセット:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは、[マルチセット:: size (STL/CLR)](../dotnet/multiset-size-stl-clr.md)`() == 0`に相当します。 このメソッドは、マルチセットが空かどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_multiset_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="multisetend-stlclr"></a><a name="end"></a>マルチセット:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示す双方向反復子を返します。 このメソッドを使用して、被制御シーケンスの末尾を指定する反復子を取得します。被制御シーケンスの長さが変更されている場合、その状態は変わりません。

### <a name="example"></a>例

```cpp
// cliext_multiset_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    Mymultiset::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
```

## <a name="multisetequal_range-stlclr"></a><a name="equal_range"></a>マルチセット:: equal_range (STL/CLR)

指定したキーに一致する範囲を検索します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、[マルチセット:: lower_bound (stl/clr)](../dotnet/multiset-lower-bound-stl-clr.md)`(key),`[マルチセット:: upper_bound (stl/clr)](../dotnet/multiset-upper-bound-stl-clr.md)`(key))``cliext::pair<iterator, iterator>(` 反復子のペアを返します。 このメソッドを使用して、被制御シーケンス内の指定したキーに一致する要素の範囲を特定します。

### <a name="example"></a>例

```cpp
// cliext_multiset_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
typedef Mymultiset::pair_iter_iter Pairii;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display results of failed search
    Pairii pair1 = c1.equal_range(L'x');
    System::Console::WriteLine("equal_range(L'x') empty = {0}",
        pair1.first == pair1.second);

    // display results of successful search
    pair1 = c1.equal_range(L'b');
    for (; pair1.first != pair1.second; ++pair1.first)
        System::Console::Write("{0} ", *pair1.first);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
equal_range(L'x') empty = True
b
```

## <a name="multiseterase-stlclr"></a><a name="erase"></a>マルチセット:: erase (STL/CLR)

指定した位置にある要素を削除します。

### <a name="syntax"></a>構文

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
size_type erase(key_type key)
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
消去する範囲の先頭。

*key*<br/>
消去するキー値。

*last*<br/>
消去する範囲の末尾。

*where*<br/>
消去する要素。

### <a name="remarks"></a>解説

最初のメンバー関数*は、が*指す被制御シーケンスの要素を削除し、削除された要素の後の最初の要素を指定する反復子を返します。そのような要素が存在しない場合は、[マルチセット:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()` します。 このメソッドを使用して、1つの要素を削除します。

2番目のメンバー関数は、被制御シーケンスの要素を [`first`、`last`) の範囲で削除し、削除された要素の後に残っている最初の要素を指定する反復子を返します。そのような要素が存在しない場合は `end()` します。 これを使用して、0個以上の連続する要素を削除します。

3番目のメンバー関数は、キーの順序が同じ*キーを持つ*被制御シーケンスの要素を削除し、削除された要素の数を返します。 これを使用して、指定されたキーに一致するすべての要素を削除およびカウントします。

各要素の消去では、被制御シーケンス内の要素数の対数に比例して時間がかかります。

### <a name="example"></a>例

```cpp
// cliext_multiset_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.insert(L'd');
    c1.insert(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    Mymultiset::iterator it = c1.end();
    System::Console::WriteLine("erase(begin(), end()-1) = {0}",
        *c1.erase(c1.begin(), --it));
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
    }
```

```Output
a b c
erase(begin()) = b
b c d e
erase(begin(), end()-1) = e
size() = 1
```

## <a name="multisetfind-stlclr"></a><a name="find"></a>マルチセット:: find (STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

被制御シーケンス内の少なくとも1つの要素の順序が同じである*場合、メンバー*関数は、これらの要素のいずれかを指定する反復子を返します。それ以外の場合は、[マルチセット:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`を返します。 このメソッドを使用して、被制御シーケンス内で、指定したキーに一致する要素を検索します。

### <a name="example"></a>例

```cpp
// cliext_multiset_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("find {0} = {1}",
        L'A', c1.find(L'A') != c1.end());
    System::Console::WriteLine("find {0} = {1}",
        L'b', *c1.find(L'b'));
    System::Console::WriteLine("find {0} = {1}",
        L'C', c1.find(L'C') != c1.end());
    return (0);
    }
```

```Output
a b c
find A = False
find b = b
find C = False
```

## <a name="multisetgeneric_container-stlclr"></a><a name="generic_container"></a>マルチセット:: generic_container (STL/CLR)

コンテナーのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.insert(L'e');
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c d
a b c d e
```

## <a name="multisetgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>マルチセット:: generic_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_iterator gcit = gc1->begin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="multisetgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>マルチセット:: generic_reverse_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する逆順反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反転反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_reverse_iterator gcit = gc1->rbegin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="multisetgeneric_value-stlclr"></a><a name="generic_value"></a>マルチセット:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する `GValue` 型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mymultiset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get an element and display it
    Mymultiset::generic_iterator gcit = gc1->begin();
    Mymultiset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="multisetinsert-stlclr"></a><a name="insert"></a>マルチセット:: insert (STL/CLR)

要素を追加します。

### <a name="syntax"></a>構文

```cpp
iterator insert(value_type val);
iterator insert(iterator where, value_type val);
template<typename InIter>
    void insert(InIter first, InIter last);
void insert(System::Collections::Generic::IEnumerable<value_type>^ right);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*right*<br/>
挿入する列挙体。

*val*<br/>
挿入するキー値。

*where*<br/>
コンテナー内の挿入位置 (ヒントのみ)。

### <a name="remarks"></a>解説

各メンバー関数は、残りのオペランドによって指定されたシーケンスを挿入します。

1つ目のメンバー関数は、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 1つの要素を挿入するために使用します。

2番目のメンバー関数は、(パフォーマンスを向上させるために) ヒントと*してを使用し*て、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 これを使用して、既知の要素に隣接している可能性のある単一の要素を挿入します。

3番目のメンバー関数は、シーケンス [`first`、`last`) を挿入します。 このメソッドを使用して、別のシーケンスからコピーされた0個以上の要素を挿入します。

4番目のメンバー関数は、*右側*に指定されたシーケンスを挿入します。 このメソッドを使用して、列挙子によって記述されたシーケンスを挿入します。

各要素の挿入には、被制御シーケンス内の要素数の対数に比例した時間がかかります。 挿入ポイントに隣接する要素を指定するヒントを指定すると、挿入は償却定数時間で実行できます。

### <a name="example"></a>例

```cpp
// cliext_multiset_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value, unique and duplicate
    System::Console::WriteLine("insert(L'x') = {0}",
        *c1.insert(L'x'));

    System::Console::WriteLine("insert(L'b') = {0}",
        *c1.insert(L'b'));

    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value with hint
    System::Console::WriteLine("insert(begin(), L'y') = {0}",
        *c1.insert(c1.begin(), L'y'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    Mymultiset c2;
    Mymultiset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    Mymultiset c3;
    c3.insert(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
insert(L'x') = x
insert(L'b') = b
a b b c x
insert(begin(), L'y') = y
a b b c x y
a b b c x
a b b c x y
```

## <a name="multisetiterator-stlclr"></a><a name="iterator"></a>マルチセット:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの双方向反復子として使用できる、未指定の型 `T1` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    Mymultiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetkey_comp-stlclr"></a><a name="key_comp"></a>マルチセット:: key_comp (STL/CLR)

2つのキーの順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 2 つのキーを比較する場合にこれを使用します。

### <a name="example"></a>例

```cpp
// cliext_multiset_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="multisetkey_compare-stlclr"></a><a name="key_compare"></a>マルチセット:: key_compare (STL/CLR)

2つのキーの順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>解説

この型は、キー引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_multiset_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mymultiset c2 = cliext::greater<wchar_t>();
    kcomp = c2.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False

compare(L'a', L'a') = False
compare(L'a', L'b') = False
compare(L'b', L'a') = True
```

## <a name="multisetkey_type-stlclr"></a><a name="key_type"></a>マルチセット:: key_type (STL/CLR)

順序付けキーの型です。

### <a name="syntax"></a>構文

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター*キー*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_multiset_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using key_type
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Mymultiset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetlower_bound-stlclr"></a><a name="lower_bound"></a>マルチセット:: lower_bound (STL/CLR)

指定されたキーに一致する範囲の先頭を検索します。

### <a name="syntax"></a>構文

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*への順序が同じである被制御シーケンス内の最初の要素 `X` を決定します。 そのような要素が存在しない場合は、[マルチセット:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; を返します。それ以外の場合は、`X`を指定する反復子を返します。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの先頭を検索します。

### <a name="example"></a>例

```cpp
// cliext_multiset_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("lower_bound(L'x')==end() = {0}",
        c1.lower_bound(L'x') == c1.end());

    System::Console::WriteLine("*lower_bound(L'a') = {0}",
        *c1.lower_bound(L'a'));
    System::Console::WriteLine("*lower_bound(L'b') = {0}",
        *c1.lower_bound(L'b'));
    return (0);
    }
```

```Output
a b c
lower_bound(L'x')==end() = True
*lower_bound(L'a') = a
*lower_bound(L'b') = b
```

## <a name="multisetmake_value-stlclr"></a><a name="make_value"></a>マルチセット:: make_value (STL/CLR)

値オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
使用するキー値。

### <a name="remarks"></a>解説

このメンバー関数は、キーが*キー*である `value_type` オブジェクトを返します。 これを使用して、他のいくつかのメンバー関数との使用に適したオブジェクトを作成します。

### <a name="example"></a>例

```cpp
// cliext_multiset_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(Mymultiset::make_value(L'a'));
    c1.insert(Mymultiset::make_value(L'b'));
    c1.insert(Mymultiset::make_value(L'c'));

    // display contents " a b c"
    for each (Mymultiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetmultiset-stlclr"></a><a name="multiset"></a>マルチセット:: マルチセット (STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
multiset();
explicit multiset(key_compare^ pred);
multiset(multiset<Key>% right);
multiset(multiset<Key>^ right);
template<typename InIter>
    multisetmultiset(InIter first, InIter last);
template<typename InIter>
    multiset(InIter first, InIter last,
        key_compare^ pred);
multiset(System::Collections::Generic::IEnumerable<GValue>^ right);
multiset(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*pred*<br/>
被制御シーケンスの順序付け述語。

*right*<br/>
挿入するオブジェクトまたは範囲。

### <a name="remarks"></a>解説

コンストラクター:

`multiset();`

既定の順序述語 `key_compare()`を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、既定の順序述語を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`explicit multiset(key_compare^ pred);`

順序述語*pred*を使用して、要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、指定された順序述語を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`multiset(multiset<Key>% right);`

既定の順序述語を使用して、シーケンス [`right.begin()`、`right.end()`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、既定の順序述語を使用して、マルチセットオブジェクト*権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。

コンストラクター:

`multiset(multiset<Key>^ right);`

既定の順序述語を使用して、シーケンス [`right->begin()`、`right->end()`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、既定の順序述語を使用して、マルチセットオブジェクト*権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。

コンストラクター:

`template<typename InIter> multiset(InIter first, InIter last);`

既定の順序述語を使用して、シーケンス [`first`、`last`) を使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを別のシーケンスのコピーにし、既定の順序述語を使用します。

コンストラクター:

`template<typename InIter> multiset(InIter first, InIter last, key_compare^ pred);`

順序述語*pred*を使用して、被制御シーケンスを [`first`、`last`) のシーケンスで初期化します。 このメソッドを使用して、被制御シーケンスを、指定した順序述語を使用して別のシーケンスのコピーにします。

コンストラクター:

`multiset(System::Collections::Generic::IEnumerable<Key>^ right);`

既定の順序述語を使用して、列挙子*権限*によって指定されたシーケンスを使用して被制御シーケンスを初期化します。 このメソッドは、既定の順序述語を使用して、被制御シーケンスを、列挙子によって記述された別のシーケンスのコピーにするために使用します。

コンストラクター:

`multiset(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

順序付け述語*pred*を使用して、列挙子*権限*によって指定されたシーケンスを使用して被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、指定した順序述語を使用して、列挙子によって記述された別のシーケンスのコピーを作成します。

### <a name="example"></a>例

```cpp
// cliext_multiset_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
// construct an empty container
    Mymultiset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mymultiset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mymultiset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mymultiset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    Mymultiset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration and an ordering rule
    Mymultiset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mymultiset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mymultiset c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
a b c
size() = 0
c b a
a b c
c b a
a b c
c b a
c b a
a b c
```

## <a name="multisetoperator-stlclr"></a><a name="op_as"></a>マルチセット:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
multiset<Key>% operator=(multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに*right*をコピーし、`*this`を返します。 このメソッドを使用して、被制御シーケンスを*右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (Mymultiset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2 = c1;
// display contents " a b c"
    for each (Mymultiset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="multisetrbegin-stlclr"></a><a name="rbegin"></a>マルチセット:: rbegin (STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素、または空のシーケンスの先頭の次の位置を指定する反転反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_multiset_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    Mymultiset::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
```

## <a name="multisetreference-stlclr"></a><a name="reference"></a>マルチセット:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    Mymultiset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Mymultiset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="multisetrend-stlclr"></a><a name="rend"></a>マルチセット:: rend (STL/CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの先頭を越えた位置を示す反転反復子を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_multiset_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mymultiset::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
```

## <a name="multisetreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>マルチセット:: reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの反転反復子として使用できる、未指定の型 `T3` のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" reversed
    Mymultiset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="multisetsize-stlclr"></a><a name="size"></a>マルチセット:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスにゼロ以外のサイズがあるかどうかについては、「[マルチセット:: empty (STL/CLR)](../dotnet/multiset-empty-stl-clr.md)`()`」を参照してください。

### <a name="example"></a>例

```cpp
// cliext_multiset_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.insert(L'a');
    c1.insert(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
a b c
size() = 3 starting with 3
size() = 0 after clearing
size() = 2 after adding 2
```

## <a name="multisetsize_type-stlclr"></a><a name="size_type"></a>マルチセット:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_multiset_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mymultiset::size_type diff = 0;
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="multisetswap-stlclr"></a><a name="swap"></a>マルチセット:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、`this` と*right*の間で被制御シーケンスを交換します。 この処理は一定時間に実行され、例外はスローされません。 2つのコンテナーの内容を簡単に交換する方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_multiset_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    Mymultiset c2;
    c2.insert(L'd');
    c2.insert(L'e');
    c2.insert(L'f');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // swap and redisplay
    c1.swap(c2);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
d e f
d e f
a b c
```

## <a name="multisetto_array-stlclr"></a><a name="to_array"></a>マルチセット:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_multiset_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.insert(L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display the earlier array copy
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c d
a b c
```

## <a name="multisetupper_bound-stlclr"></a><a name="upper_bound"></a>マルチセット:: upper_bound (STL/CLR)

指定されたキーに一致する範囲の末尾を検索します。

### <a name="syntax"></a>構文

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

このメンバー関数は、*キー*への順序が同じである被制御シーケンス内の `X` 最後の要素を決定します。 そのような要素が存在しない場合、または被制御シーケンスの最後の要素が `X` の場合は、[マルチセット:: end (STL/CLR)](../dotnet/multiset-end-stl-clr.md)`()`; を返します。それ以外の場合は、`X`を超えて最初の要素を指定する反復子を返します。 このメソッドを使用して、被制御シーケンスの中で、指定したキーに一致する要素のシーケンスの末尾を検索します。

### <a name="example"></a>例

```cpp
// cliext_multiset_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("upper_bound(L'x')==end() = {0}",
        c1.upper_bound(L'x') == c1.end());

    System::Console::WriteLine("*upper_bound(L'a') = {0}",
        *c1.upper_bound(L'a'));
    System::Console::WriteLine("*upper_bound(L'b') = {0}",
        *c1.upper_bound(L'b'));
    return (0);
    }
```

```Output
a b c
upper_bound(L'x')==end() = True
*upper_bound(L'a') = b
*upper_bound(L'b') = c
```

## <a name="multisetvalue_comp-stlclr"></a><a name="value_comp"></a>マルチセット:: value_comp (STL/CLR)

2つの要素の値の順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 これを使用して、2つの要素の値を比較します。

### <a name="example"></a>例

```cpp
// cliext_multiset_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="multisetvalue_compare-stlclr"></a><a name="value_compare"></a>マルチセット:: value_compare (STL/CLR)

2つの要素の値の順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>解説

この型は、値引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_multiset_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    Mymultiset::value_compare^ kcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(L'a', L'a') = False
compare(L'a', L'b') = True
compare(L'b', L'a') = False
```

## <a name="multisetvalue_type-stlclr"></a><a name="value_type"></a>マルチセット:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>解説

この型は `generic_value`の同意語です。

### <a name="example"></a>例

```cpp
// cliext_multiset_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c" using value_type
    for (Mymultiset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Mymultiset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-multiset-stlclr"></a><a name="op_neq"></a>operator! = (マルチセット) (STL/CLR)

リストが等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator!=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(left == right)`を返します。 このメソッドを使用して、2つのマルチセットが要素ごとに比較されるときに、 *left*が*right*と同じ順序で並んでいないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] != [a b c] is {0}",
        c1 != c1);
    System::Console::WriteLine("[a b c] != [a b d] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] != [a b c] is False
[a b c] != [a b d] is True
```

## <a name="operatorlt-multiset-stlclr"></a><a name="op_lt"></a>operator&lt; (マルチセット) (STL/CLR)

比較より小さいリスト。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator<(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

Operator 関数は、`!(right[i] < left[i])` が `left[i] < right[i]`にも当てはまる `i` 最小の位置に対して true を返します。 それ以外の場合は `left->size() < right->size()` を返します。このメソッドを使用して、2つのマルチセットが要素別に比較されるときに、 *left*が*right*の前に並べられるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] < [a b c] is {0}",
        c1 < c1);
    System::Console::WriteLine("[a b c] < [a b d] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] < [a b c] is False
[a b c] < [a b d] is True
```

## <a name="operatorlt-multiset-stlclr"></a><a name="op_lteq"></a>operator&lt;= (マルチセット) (STL/CLR)

以下を比較します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator<=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(right < left)`を返します。 このメソッドを使用して、2つのマルチセットが要素別に比較されたときに、 *right*の後に*left*が順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] <= [a b c] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[a b d] <= [a b c] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] <= [a b c] is True
[a b d] <= [a b c] is False
```

## <a name="operator-multiset-stlclr"></a><a name="op_eq"></a>operator = = (マルチセット) (STL/CLR)

同じ比較を一覧表示します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator==(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、 *left*と*right*で制御されるシーケンスの長さが同じで、`i`位置ごとに `right[i]``left[i] ==` 場合にのみ true を返します。 このメソッドを使用して、2つのマルチセットが要素ごとに比較されるときに、 *left*が*right*と同じ順序で並んでいるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] == [a b c] is {0}",
        c1 == c1);
    System::Console::WriteLine("[a b c] == [a b d] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] == [a b c] is True
[a b c] == [a b d] is False
```

## <a name="operatorgt-multiset-stlclr"></a><a name="op_gt"></a>operator&gt; (マルチセット) (STL/CLR)

比較よりも大きいリストです。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator>(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

Operator 関数は、`left``<` `right` を返します。 このメソッドを使用して、2つのマルチセットが要素ごとに比較されたときに、 *right*の後に*左*を並べるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] > [a b c] is {0}",
        c1 > c1);
    System::Console::WriteLine("[a b d] > [a b c] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] > [a b c] is False
[a b d] > [a b c] is True
```

## <a name="operatorgt-multiset-stlclr"></a><a name="op_gteq"></a>operator&gt;= (マルチセット) (STL/CLR)

以上の比較を一覧表示します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator>=(multiset<Key>% left,
        multiset<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(left < right)`を返します。 このメソッドを使用して、2つのマルチセットが要素別に比較されるときに、 *left*が*right*の前に順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_multiset_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::multiset<wchar_t> Mymultiset;
int main()
    {
    Mymultiset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mymultiset c2;
    c2.insert(L'a');
    c2.insert(L'b');
    c2.insert(L'd');

    // display contents " a b d"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("[a b c] >= [a b c] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[a b c] >= [a b d] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
a b c
a b d
[a b c] >= [a b c] is True
[a b c] >= [a b d] is False
```
