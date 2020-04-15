---
title: set (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::set
- cliext::set::begin
- cliext::set::clear
- cliext::set::const_iterator
- cliext::set::const_reference
- cliext::set::const_reverse_iterator
- cliext::set::count
- cliext::set::difference_type
- cliext::set::empty
- cliext::set::end
- cliext::set::equal_range
- cliext::set::erase
- cliext::set::find
- cliext::set::generic_container
- cliext::set::generic_iterator
- cliext::set::generic_reverse_iterator
- cliext::set::generic_value
- cliext::set::insert
- cliext::set::iterator
- cliext::set::key_comp
- cliext::set::key_compare
- cliext::set::key_type
- cliext::set::lower_bound
- cliext::set::make_value
- cliext::set::operator=
- cliext::set::rbegin
- cliext::set::reference
- cliext::set::rend
- cliext::set::reverse_iterator
- cliext::set::set
- cliext::set::size
- cliext::set::size_type
- cliext::set::swap
- cliext::set::to_array
- cliext::set::upper_bound
- cliext::set::value_comp
- cliext::set::value_compare
- cliext::set::value_type
helpviewer_keywords:
- <cliext/set> header [STL/CLR]
- <set> header [STL/CLR]
- set class [STL/CLR]
- operator!= (set) member [STL/CLR]
- operator< (set) member [STL/CLR]
- operator<= (set) member [STL/CLR]
- operator== (set) member [STL/CLR]
- operator> (set) member [STL/CLR]
- operator>= (set) member [STL/CLR]
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
- operator= member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reverse_iterator member [STL/CLR]
- set member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- upper_bound member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 27d3628c-741a-43a7-bef1-5085536f679e
ms.openlocfilehash: 38b0a3278efd10ef5cc989a5fc900bf82d377eae
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320306"
---
# <a name="set-stlclr"></a>set (STL/CLR)

テンプレート クラスは、双方向アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナー`set`を使用して、(ほぼ) バランスの取れた順序付けられたノードツリーとして要素のシーケンスを管理し、それぞれが 1 つの要素を格納します。

以下の説明では、`GValue`は と同`GKey`じですが、後者が ref 型でない限り *、キー*と同じです`Key^`。

## <a name="syntax"></a>構文

```cpp
template<typename Key>
    ref class set
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

*キー*<br/>
被制御シーケンス内の要素のキー コンポーネントの型。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<クライト/セット>

**名前空間:** クエクスキ

## <a name="declarations"></a>宣言

|型定義|説明|
|---------------------|-----------------|
|[set::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[set::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[set::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[set::difference_type (STL/CLR)](#difference_type)|2 つの要素間の (符号付きの可能性がある) 距離の型。|
|[set::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリック インターフェイスの型。|
|[set::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリック インターフェイスの反復器の型。|
|[set::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリック インターフェイスの逆反復器の型。|
|[set::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリック インターフェイスの要素の型。|
|[set::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[set::key_compare (STL/CLR)](#key_compare)|2 つのキーの順序付けデリゲート。|
|[set::key_type (STL/CLR)](#key_type)|順序付けキーの型です。|
|[set::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[set::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[set::size_type (STL/CLR)](#size_type)|2 つの要素間の (負でない) 距離の型。|
|[set::value_compare (STL/CLR)](#value_compare)|2 つの要素値の順序付けデリゲート。|
|[set::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[set::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[set::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[set::count (STL/CLR)](#count)|指定したキーに一致する要素をカウントします。|
|[set::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[set::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[set::equal_range (STL/CLR)](#equal_range)|指定したキーに一致する範囲を検索します。|
|[set::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[set::find (STL/CLR)](#find)|指定したキーに一致する要素を検索します。|
|[set::insert (STL/CLR)](#insert)|要素を追加します。|
|[set::key_comp (STL/CLR)](#key_comp)|2 つのキーの順序付けデリゲートをコピーします。|
|[set::lower_bound (STL/CLR)](#lower_bound)|指定したキーに一致する範囲の先頭を検索します。|
|[set::make_value (STL/CLR)](#make_value)|値オブジェクトを構築します。|
|[set::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[set::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[set::set (STL/CLR)](#set)|コンテナー オブジェクトを構築します。|
|[set::size (STL/CLR)](#size)|要素の数をカウントします。|
|[set::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[set::to_array (STL/CLR)](#to_array)|制御されたシーケンスを新しい配列にコピーします。|
|[set::upper_bound (STL/CLR)](#upper_bound)|指定したキーに一致する範囲の末尾を検索します。|
|[set::value_comp (STL/CLR)](#value_comp)|2 つの要素値の順序付けデリゲートをコピーします。|

|演算子|説明|
|--------------|-----------------|
|[set::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[演算子!= (セット) (STL/CLR)](#op_neq)|オブジェクトが別`set``set`のオブジェクトと等しくないかどうかを判断します。|
|[演算子< (セット) (STL/CLR)](#op_lt)|オブジェクトが別`set``set`のオブジェクトより小さいかどうかを判断します。|
|[演算子<= (セット) (STL/CLR)](#op_lteq)|オブジェクトが別`set``set`のオブジェクト以下かどうかを判断します。|
|[operator== (set) (STL/CLR)](#op_eq)|オブジェクトが別`set``set`のオブジェクトと等しいかどうかを判断します。|
|[演算子> (セット) (STL/CLR)](#op_gt)|オブジェクトが別`set``set`のオブジェクトより大きいかどうかを判断します。|
|[演算子>= (セット) (STL/CLR)](#op_gteq)|オブジェクトが別`set``set`のオブジェクト以上かどうかを判断します。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製する。|
|<xref:System.Collections.IEnumerable>|要素を通してシーケンスします。|
|<xref:System.Collections.ICollection>|要素のグループを管理します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を通してシーケンスします。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|
|ITree\<キー、値>|汎用コンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、個別のノードとして制御するシーケンスのストレージを割り当てて解放します。 要素を (ほぼ) バランスの取れたツリーに挿入し、ノード間のリンクを変更して順序を保ち、あるノードの内容を別のノードにコピーすることはありません。 つまり、残りの要素を邪魔することなく、自由に要素を挿入したり削除したりできます。

オブジェクトは[、set::key_compare (STL/CLR)](../dotnet/set-key-compare-stl-clr.md)型の格納されたデリゲート オブジェクトを呼び出すことによって、制御するシーケンスを順序付けます。 セットを構築するときに、格納されているデリゲート オブジェクトを指定できます。デリゲート オブジェクトを指定しない場合、既定の比較は`operator<(key_type, key_type)`比較です。 このストアド オブジェクトにアクセスする場合は、メンバー関数[set::key_comp (STL/CLR)](../dotnet/set-key-comp-stl-clr.md)`()`を呼び出します。

このようなデリゲート オブジェクトは[、set::key_type (STL/CLR)](../dotnet/set-key-type-stl-clr.md)の型のキーに厳密な弱い順序を課す必要があります。 つまり、任意の 2`X`つの`Y`キーと :

`key_comp()(X, Y)`は、呼び出しごとに同じブール値の結果を返します。

true`key_comp()(X, Y)`の場合`key_comp()(Y, X)`は、false にする必要があります。

true`key_comp()(X, Y)`の場合`X`は、 の前に注文`Y`されると言われます。

もし`!key_comp()(X, Y) && !key_comp()(Y, X)`真であれば、`X`同等`Y`の順序を持っていると言われます。

制御シーケンス`X``Y`の前にある要素の場合は false`key_comp()(Y, X)`です。 (既定のデリゲート オブジェクトの場合、キーの値は減少しません)。テンプレート クラス[セット](../dotnet/set-stl-clr.md)とは異なり、`set`テンプレート クラスのオブジェクトでは、すべての要素のキーが一意である必要はありません。 (2 つ以上のキーの順序は同等です)。

各要素は、ey と値の両方として機能します。 シーケンスは、シーケンス内の要素の数の対数に比例した操作の数 (対数時間) を使用して任意の要素の参照、挿入、および削除を可能にする方法で表されます。 要素を挿入しても反復子の有効性は失われません。また、要素を削除した場合は、削除された要素を指す反復子だけが無効化されます。

セットは双方向反復子をサポートするため、制御シーケンス内の要素を指定する反復子を指定して、隣接する要素にステップインできます。 特殊なヘッド ノードは[、set::end (STL/CLR)](../dotnet/set-end-stl-clr.md)`()`によって返される反復器に対応します。 この反復子をデクリメントして、被制御シーケンス内の最後の要素に到達できます (存在する場合)。 セット反復器をインクリメントしてヘッド ノードに到達すると、次に`end()`と等しくなります。 しかし、 によって返された`end()`反復器を逆参照することはできません。

ランダム アクセス反復子を必要とする数値位置を指定して、set 要素を直接参照することはできません。

セット反復器は、関連付けられたセット ノードへのハンドルを格納し、それに関連付けられたコンテナーへのハンドルを格納します。 反復子は、関連付けられたコンテナー オブジェクトでのみ使用できます。 セット反復器は、関連付けられたセットノードが一部のセットに関連付けられている限り有効です。 さらに、有効な反復子は逆参照可能であり、指定した要素値にアクセスしたり変更したりするために使用できます`end()`。

要素を削除または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナを破棄すると、すべての要素が消去されます。 したがって、要素型が ref クラスであるコンテナーは、コンテナーより長い要素が存在することを保証します。 ただし、ハンドルのコンテナーは要素を破棄*しないこと*に注意してください。

## <a name="members"></a>メンバー

## <a name="setbegin-stlclr"></a><a name="begin"></a>セット::開始(STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最初の要素を指定する双方向反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_set_begin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::iterator it = c1.begin();
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

## <a name="setclear-stlclr"></a><a name="clear"></a>セット::クリア(STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

メンバー関数は効果的に[set::消去 (STL/CLR)](../dotnet/set-erase-stl-clr.md)`(`セットを呼び出します[: 開始 (STL/CLR)](../dotnet/set-begin-stl-clr.md) `(),` [セット::終了 (STL/CLR)](../dotnet/set-end-stl-clr.md)`())`. これを使用して、制御されたシーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_set_clear.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setconst_iterator-stlclr"></a><a name="const_iterator"></a>セット::const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの一定`T2`の双方向反復器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_set_const_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reference-stlclr"></a><a name="const_reference"></a>セット::const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_set_const_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        Myset::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>セット::const_reverse_iterator (STL/CLR)

制御シーケンスの定数逆反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数逆`T4`反復器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_set_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::const_reverse_iterator crit = c1.rbegin();
    for (; crit != c1.rend(); ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setcount-stlclr"></a><a name="count"></a>セット::カウント (STL/CLR)

指定したキーに一致する要素の数を検索します。

### <a name="syntax"></a>構文

```cpp
size_type count(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

メンバー関数は *、key*と同等の順序を持つ、制御されたシーケンス内の要素の数を返します。 被制御シーケンス内の指定したキーに一致する現在の要素の数を確認する場合に、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_set_count.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setdifference_type-stlclr"></a><a name="difference_type"></a>セット::difference_type (STL/CLR)

2 つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

型は、負の要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_set_difference_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::difference_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (Myset::iterator it = c1.end(); it != c1.begin(); --it)
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

## <a name="setempty-stlclr"></a><a name="empty"></a>セット::空(STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[、設定と同等です::サイズ(STL/CLR)](../dotnet/set-size-stl-clr.md)`() == 0` セットが空かどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_empty.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setend-stlclr"></a><a name="end"></a>セット::終了 (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの末尾を越えた方向反復器を返します。 これを使用して、制御シーケンスの終了を指定する反復器を取得します。制御シーケンスの長さが変更された場合、そのステータスは変更されません。

### <a name="example"></a>例

```cpp
// cliext_set_end.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    Myset::iterator it = c1.end();
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

## <a name="setequal_range-stlclr"></a><a name="equal_range"></a>セット::equal_range (STL/CLR)

指定したキーに一致する範囲を検索します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, iterator> equal_range(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

メンバー`cliext::pair<iterator, iterator>(`関数は、反復子セットのペアを返します[:::lower_bound (STL/CLR)](../dotnet/set-lower-bound-stl-clr.md) `(key),` [セット::upper_bound (STL/CLR)](../dotnet/set-upper-bound-stl-clr.md)`(key))`。 このキーを使用して、指定したキーに一致する、現在の制御シーケンス内の要素の範囲を決定します。

### <a name="example"></a>例

```cpp
// cliext_set_equal_range.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_iter Pairii;
int main()
    {
    Myset c1;
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

## <a name="seterase-stlclr"></a><a name="erase"></a>セット::消去(STL /CLR)

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
消去する範囲の終わり。

*where*<br/>
消去する要素。

### <a name="remarks"></a>解説

最初のメンバー関数は、 が指す制御シーケンスの要素を*削除*し、削除された要素を超えて残っている最初の要素を示す反復[子を返](../dotnet/set-end-stl-clr.md)`()`します。 1 つの要素を削除する場合に使用します。

2 番目のメンバー関数は、範囲 [`first`, )`last`の制御シーケンスの要素を削除し、削除された要素を超えて残っている最初の要素を指定`end()`する反復子を返します。 この値を使用して、連続する要素を 0 個以上削除します。

3 番目のメンバー関数は、key と同等の順序を持つ、制御されたシーケンスの*要素を削除*し、削除された要素の数を返します。 これを使用して、指定したキーに一致するすべての要素を削除し、カウントします。

各要素消去は、被制御シーケンス内の要素数の対数に比例して時間がかかります。

### <a name="example"></a>例

```cpp
// cliext_set_erase.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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
    Myset::iterator it = c1.end();
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

## <a name="setfind-stlclr"></a><a name="find"></a>設定::検索(STL/CLR)

指定したキーに一致する要素を検索します。

### <a name="syntax"></a>構文

```cpp
iterator find(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

制御シーケンス内の少なくとも 1 つの要素が*key*と同等の順序を持つ場合、メンバー関数は、それらの要素の 1 つを指定する反復子を返します。それ以外の場合は[、set::end (STL/CLR) を](../dotnet/set-end-stl-clr.md)`()`返します。 このキーを使用して、指定したキーに一致する、現在の制御シーケンス内の要素を検索します。

### <a name="example"></a>例

```cpp
// cliext_set_find.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setgeneric_container-stlclr"></a><a name="generic_container"></a>セット::generic_container (STL/CLR)

コンテナーのジェネリック インターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    ITree<GKey, GValue>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_set_generic_container.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
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

## <a name="setgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>設定::generic_iterator (STL/CLR)

コンテナーのジェネリック インターフェイスで使用する反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerBidirectionalIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスで使用できるジェネリック反復器を表します。

### <a name="example"></a>例

```cpp
// cliext_set_generic_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>設定::generic_reverse_iterator (STL/CLR)

コンテナのジェネリック インターフェイスで使用するリバース反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value>
    generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスで使用できる汎用リバース 反復処理を表します。

### <a name="example"></a>例

```cpp
// cliext_set_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_reverse_iterator gcit = gc1->rbegin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
c
```

## <a name="setgeneric_value-stlclr"></a><a name="generic_value"></a>セット::generic_value (STL/CLR)

コンテナーのジェネリック インターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー`GValue`クラスのジェネリック インターフェイスで使用する格納された要素の値を記述する型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_set_generic_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myset::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get an element and display it
    Myset::generic_iterator gcit = gc1->begin();
    Myset::generic_value gcval = *gcit;
    System::Console::WriteLine("{0} ", gcval);
    return (0);
    }
```

```Output
a b c
a b c
a
```

## <a name="setinsert-stlclr"></a><a name="insert"></a>セット::挿入(STL/CLR)

要素を追加します。

### <a name="syntax"></a>構文

```cpp
cliext::pair<iterator, bool> insert(value_type val);
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

*そうです*<br/>
挿入する列挙体。

*ヴァル*<br/>
挿入するキー値。

*where*<br/>
挿入するコンテナー内の場所 (ヒントのみ)。

### <a name="remarks"></a>解説

各メンバー関数は、残りのオペランドで指定されたシーケンスを挿入します。

最初のメンバー関数は、value *val*を持つ要素を挿入しようと試み、`X`値のペアを返します。 true`X.second`の場合`X.first`は、新しく挿入された要素を指定します。それ`X.first`以外の場合は、既に存在し、新しい要素が挿入されていない、同等の順序を持つ要素を指定します。 この要素を使用して、1 つの要素を挿入します。

2 番目のメンバー関数は *、value* *val*を使用して要素をヒントとして (パフォーマンスを向上させるために) 挿入し、新しく挿入された要素を指定する反復子を返します。 このコードを使用して、知っている要素に隣接する可能性のある単一の要素を挿入します。

3 番目のメンバー関数はシーケンス`first`[ `last`, を挿入します。 別のシーケンスからコピーした要素を 0 個以上挿入する場合に使用します。

4 番目のメンバー関数は、*右*で指定されたシーケンスを挿入します。 列挙子によって記述されたシーケンスを挿入する場合に使用します。

各要素の挿入は、制御されたシーケンス内の要素数の対数に比例します。 ただし、挿入ポイントに隣接する要素を指定するヒントを指定すると、固定定数時間内に挿入が発生する可能性があります。

### <a name="example"></a>例

```cpp
// cliext_set_insert.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
typedef Myset::pair_iter_bool Pairib;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value, unique and duplicate
    Pairib pair1 = c1.insert(L'x');
    System::Console::WriteLine("insert(L'x') = [{0} {1}]",
        *pair1.first, pair1.second);

    pair1 = c1.insert(L'b');
    System::Console::WriteLine("insert(L'b') = [{0} {1}]",
        *pair1.first, pair1.second);

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
    Myset c2;
    Myset::iterator it = c1.end();
    c2.insert(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert an enumeration
    Myset c3;
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
insert(L'x') = [x True]
insert(L'b') = [b False]
a b c x
insert(begin(), L'y') = y
a b c x y
a b c x
a b c x y
```

## <a name="setiterator-stlclr"></a><a name="iterator"></a>セット::反復器(STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの双方向反復`T1`器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_set_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setkey_comp-stlclr"></a><a name="key_comp"></a>セット::key_comp (STL/CLR)

2 つのキーの順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
key_compare^key_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、制御されたシーケンスの順序付けに使用される順序付けデリゲートを返します。 2 つのキーを比較する場合にこれを使用します。

### <a name="example"></a>例

```cpp
// cliext_set_key_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
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

## <a name="setkey_compare-stlclr"></a><a name="key_compare"></a>セット::key_compare (STL/CLR)

2 つのキーの順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<GKey, GKey, bool>
    key_compare;
```

### <a name="remarks"></a>解説

型は、キー引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_set_key_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::key_compare^ kcomp = c1.key_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        kcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        kcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        kcomp(L'b', L'a'));
    System::Console::WriteLine();

// test a different ordering rule
    Myset c2 = cliext::greater<wchar_t>();
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

## <a name="setkey_type-stlclr"></a><a name="key_type"></a>セット::key_type (STL/CLR)

順序付けキーの型です。

### <a name="syntax"></a>構文

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメータ Key のシノニム*です*。

### <a name="example"></a>例

```cpp
// cliext_set_key_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using key_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in key_type object
        Myset::key_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setlower_bound-stlclr"></a><a name="lower_bound"></a>セット::lower_bound (STL/CLR)

指定したキーに一致する範囲の先頭を検索します。

### <a name="syntax"></a>構文

```cpp
iterator lower_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

メンバー関数は、key と`X`同等の順序を持つ、制御されたシーケンス内の*最初の要素*を決定します。 そのような要素が存在しない場合は[、set::end (STL/CLR) を](../dotnet/set-end-stl-clr.md)`()`返します。それ以外の場合は、を指定する反復器`X`を返します。 このキーを使用して、指定したキーに一致する、現在の制御シーケンス内の要素のシーケンスの先頭を検索します。

### <a name="example"></a>例

```cpp
// cliext_set_lower_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setmake_value-stlclr"></a><a name="make_value"></a>セット::make_value (STL/CLR)

値オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
static value_type make_value(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
使用するキー値。

### <a name="remarks"></a>解説

メンバー関数は、key`value_type`が key である*オブジェクトを返*します。 この関数を使用して、他のいくつかのメンバー関数で使用するのに適したオブジェクトを構成します。

### <a name="example"></a>例

```cpp
// cliext_set_make_value.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(Myset::make_value(L'a'));
    c1.insert(Myset::make_value(L'b'));
    c1.insert(Myset::make_value(L'c'));

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setoperator-stlclr"></a><a name="op_as"></a>セット::演算子=(STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
set<Key>% operator=(set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバ オペレータは*オブジェクトに右*をコピーし、`*this`を返します。 これを使用して、制御されたシーケンスを*右側*の制御シーケンスのコピーに置き換えます。

### <a name="example"></a>例

```cpp
// cliext_set_operator_as.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (Myset::value_type elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
    c2 = c1;
// display contents " a b c"
    for each (Myset::value_type elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="setrbegin-stlclr"></a><a name="rbegin"></a>セット::開始(STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最後の要素を指定する逆の反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_set_rbegin.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    Myset::reverse_iterator rit = c1.rbegin();
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

## <a name="setreference-stlclr"></a><a name="reference"></a>セット::リファレンス(STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_set_reference.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    Myset::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        Myset::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="setrend-stlclr"></a><a name="rend"></a>セット::レンド(STL /CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの先頭を越えた位置を指す逆反復器を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_set_rend.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    Myset::reverse_iterator rit = c1.rend();
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

## <a name="setreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>セット::reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの反転反復`T3`器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_set_reverse_iterator.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" reversed
    Myset::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="setset-stlclr"></a><a name="set"></a>セット::セット(STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
set();
explicit set(key_compare^ pred);
set(set<Key>% right);
set(set<Key>^ right);
template<typename InIter>
    setset(InIter first, InIter last);
template<typename InIter>
    set(InIter first, InIter last,
        key_compare^ pred);
set(System::Collections::Generic::IEnumerable<GValue>^ right);
set(System::Collections::Generic::IEnumerable<GValue>^ right,
    key_compare^ pred);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*Pred*<br/>
制御シーケンスの順序付け述語。

*そうです*<br/>
挿入するオブジェクトまたは範囲。

### <a name="remarks"></a>解説

コンストラクター:

`set();`

は、既定の順序付け述語`key_compare()`を使用して、要素を持たない制御シーケンスを初期化します。 既定の順序付け述語を使用して、空の初期制御シーケンスを指定するために使用します。

コンストラクター:

`explicit set(key_compare^ pred);`

は、順序付け述語*pred*を使用して、要素を持たない制御シーケンスを初期化します。 このプロパティを使用して、指定された順序付け述語を使用して、空の初期制御シーケンスを指定します。

コンストラクター:

`set(set<Key>% right);`

は、シーケンス [`right.begin()`, )`right.end()`で、既定の順序付け述語で制御シーケンスを初期化します。 このクラスを使用して、デフォルトの順序付け述語を使用して、set オブジェクト*right*によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。

コンストラクター:

`set(set<Key>^ right);`

は、シーケンス [`right->begin()`, )`right->end()`で、既定の順序付け述語で制御シーケンスを初期化します。 このクラスを使用して、デフォルトの順序付け述語を使用して、set オブジェクト*right*によって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。

コンストラクター:

`template<typename InIter> set(InIter first, InIter last);`

は、シーケンス [`first`, )`last`で、既定の順序付け述語で制御シーケンスを初期化します。 この機能を使用すると、制御シーケンスを、デフォルトの順序付け述部を持つ別のシーケンスのコピーにします。

コンストラクター:

`template<typename InIter> set(InIter first, InIter last, key_compare^ pred);`

順序付け述語*pred*`first`を`last`使用して、順序 [ , ) で制御シーケンスを初期化します。 これを使用して、指定された順序付け述部を持つ、制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`set(System::Collections::Generic::IEnumerable<Key>^ right);`

は、既定の順序述語で、列挙子*right*で指定されたシーケンスで、制御シーケンスを初期化します。 これを使用して、制御シーケンスを列挙子によって記述された別のシーケンスのコピーに、既定の順序付け述語を使用します。

コンストラクター:

`set(System::Collections::Generic::IEnumerable<Key>^ right, key_compare^ pred);`

は、順序付け述語*pred*を使用して、列挙子*right*で指定されたシーケンスで制御シーケンスを初期化します。 これを使用して、指定された順序付け述語を持つ、列挙子によって記述された別のシーケンスのコピーを、制御シーケンスにします。

### <a name="example"></a>例

```cpp
// cliext_set_construct.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
// construct an empty container
    Myset c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an ordering rule
    Myset c2 = cliext::greater_equal<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    c2.insert(c1.begin(), c1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    Myset c3(c1.begin(), c1.end());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range and an ordering rule
    Myset c4(c1.begin(), c1.end(),
        cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    Myset c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration and an ordering rule
    Myset c6(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3,
            cliext::greater_equal<wchar_t>());
    for each (wchar_t elem in c6)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct from a generic container
    Myset c7(c4);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myset c8(%c3);
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

## <a name="setsize-stlclr"></a><a name="size"></a>セット::サイズ(STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 この値を使用して、現在の制御シーケンス内の要素の数を決定します。 シーケンスのサイズが 0 以外であるかどうかが重要な場合は[、「set::empty (STL/CLR)」](../dotnet/set-empty-stl-clr.md)`()`を参照してください。

### <a name="example"></a>例

```cpp
// cliext_set_size.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setsize_type-stlclr"></a><a name="size_type"></a>セット::size_type (STL/CLR)

2 つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_set_size_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myset::size_type diff = 0;
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="setswap-stlclr"></a><a name="swap"></a>セット::スワップ(STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

メンバー関数は、 と*の*間`this`で制御されたシーケンスを入れ替えます。 これは一定の時間で行われ、例外はスローされません。 2 つのコンテナーの内容を交換する簡単な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_set_swap.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    Myset c2;
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

## <a name="setto_array-stlclr"></a><a name="to_array"></a>設定::to_array (STL/CLR)

制御されたシーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<value_type>^ to_array();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスを含む配列を返します。 配列形式で制御シーケンスのコピーを取得するために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_to_array.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setupper_bound-stlclr"></a><a name="upper_bound"></a>セット::upper_bound (STL/CLR)

指定したキーに一致する範囲の末尾を検索します。

### <a name="syntax"></a>構文

```cpp
iterator upper_bound(key_type key);
```

#### <a name="parameters"></a>パラメーター

*key*<br/>
検索対象のキー値。

### <a name="remarks"></a>解説

メンバー関数は、key と`X`同等の順序を持つ、制御されたシーケンスの*最後の要素*を決定します。 そのような要素が存在しない場合、または`X`制御されたシーケンスの最後の要素である場合は[、set::end (STL/CLR) を](../dotnet/set-end-stl-clr.md)`()`返します。それ以外の場合は、先頭の要素を指定する反復子を`X`返します。 このキーを使用して、指定したキーに一致する、現在の制御シーケンス内の要素のシーケンスの末尾を検索します。

### <a name="example"></a>例

```cpp
// cliext_set_upper_bound.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
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

## <a name="setvalue_comp-stlclr"></a><a name="value_comp"></a>セット::value_comp (STL/CLR)

2 つの要素値の順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、制御されたシーケンスの順序付けに使用される順序付けデリゲートを返します。 この値を使用して、2 つの要素値を比較します。

### <a name="example"></a>例

```cpp
// cliext_set_value_comp.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

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

## <a name="setvalue_compare-stlclr"></a><a name="value_compare"></a>セット::value_compare (STL/CLR)

2 つの要素値の順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
Microsoft::VisualC::StlClr::BinaryDelegate<generic_value, generic_value, bool>
    value_compare;
```

### <a name="remarks"></a>解説

型は、値の引数の順序を決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_set_value_compare.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    Myset::value_compare^ kcomp = c1.value_comp();

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

## <a name="setvalue_type-stlclr"></a><a name="value_type"></a>セット::value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef generic_value value_type;
```

### <a name="remarks"></a>解説

この型は `generic_value` の同意語です。

### <a name="example"></a>例

```cpp
// cliext_set_value_type.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c" using value_type
    for (Myset::iterator it = c1.begin(); it != c1.end(); ++it)
        {   // store element in value_type object
        Myset::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-set-stlclr"></a><a name="op_neq"></a>演算子!= (セット) (STL/CLR)

リストが比較に等しくありません。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator!=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(left == right)`を返します。 2 つのセットが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_ne.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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

## <a name="operatorlt-set-stlclr"></a><a name="op_lt"></a>演算子&lt;(セット) (STL/CLR)

比較より小さいリストを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator<(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、その値も true である`i`最下位の`!(right[i] < left[i])`位置に対して`left[i] < right[i]`true を返します。 それ以外の場合`left->size() < right->size()`は、2 つのセットが要素ごとに比較されるときに *、左*が*右*より前に並べられるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_lt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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

## <a name="operatorlt-set-stlclr"></a><a name="op_lteq"></a>演算子&lt;= (セット) (STL/CLR)

比較を一覧表示します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator<=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(right < left)`を返します。 2 つのセットが要素*left*ごとに比較される場合、*左が右*の後に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_le.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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

## <a name="operator-set-stlclr"></a><a name="op_eq"></a>演算子== (セット) (STL/CLR)

等しい比較をリストします。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator==(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、*左右*で制御されるシーケンスの長さが同*right*じ場合にのみ true を返し、`i`各`left[i] ==``right[i]`位置に対して true を返します。 2 つのセットが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_eq.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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

## <a name="operatorgt-set-stlclr"></a><a name="op_gt"></a>演算子&gt;(セット) (STL/CLR)

比較より大きいリストを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator>(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`right``<``left`を返します。 2 つのセットが要素ごとに比較されるときに *、左*が*右*の後に並べ替えられたかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_gt.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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

## <a name="operatorgt-set-stlclr"></a><a name="op_gteq"></a>演算子&gt;= (セット) (STL/CLR)

比較の値が大きいか等しいかのリストを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Key>
    bool operator>=(set<Key>% left,
        set<Key>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(left < right)`を返します。 2 つのセットが要素*left*ごとに比較される場合、*左が右*より前に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_set_operator_ge.cpp
// compile with: /clr
#include <cliext/set>

typedef cliext::set<wchar_t> Myset;
int main()
    {
    Myset c1;
    c1.insert(L'a');
    c1.insert(L'b');
    c1.insert(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myset c2;
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
