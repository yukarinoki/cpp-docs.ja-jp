---
description: '詳細情報: list (STL/CLR)'
title: list (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::list
- cliext::list::assign
- cliext::list::back
- cliext::list::back_item
- cliext::list::begin
- cliext::list::clear
- cliext::list::const_iterator
- cliext::list::const_reference
- cliext::list::const_reverse_iterator
- cliext::list::difference_type
- cliext::list::empty
- cliext::list::end
- cliext::list::erase
- cliext::list::front
- cliext::list::front_item
- cliext::list::generic_container
- cliext::list::generic_iterator
- cliext::list::generic_reverse_iterator
- cliext::list::generic_value
- cliext::list::insert
- cliext::list::iterator
- cliext::list::list
- cliext::list::merge
- cliext::list::operator=
- cliext::list::pop_back
- cliext::list::pop_front
- cliext::list::push_back
- cliext::list::push_front
- cliext::list::rbegin
- cliext::list::reference
- cliext::list::remove
- cliext::list::remove_if
- cliext::list::rend
- cliext::list::resize
- cliext::list::reverse
- cliext::list::reverse_iterator
- cliext::list::size
- cliext::list::size_type
- cliext::list::sort
- cliext::list::splice
- cliext::list::swap
- cliext::list::to_array
- cliext::list::unique
- cliext::list::value_type
- cliext::operator!=(list)
- cliext::operator<(list)
- cliext::operator<=(list)
- cliext::operator==(list)
- cliext::operator>(list)
- cliext::operator>=(list)
helpviewer_keywords:
- <cliext/list> header [STL/CLR]
- list class [STL/CLR]
- <list> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- end member [STL/CLR]
- erase member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_iterator member [STL/CLR]
- generic_reverse_iterator member [STL/CLR]
- generic_value member [STL/CLR]
- insert member [STL/CLR]
- iterator member [STL/CLR]
- list member [STL/CLR]
- merge member [STL/CLR]
- operator= member [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- remove member [STL/CLR]
- remove_if member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- sort member [STL/CLR]
- splice member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- unique member [STL/CLR]
- value_type member [STL/CLR]
- operator!=(list) member [STL/CLR]
- operator<(list) member [STL/CLR]
- operator<=(list) member [STL/CLR]
- operator==(list) member [STL/CLR]
- operator>(list) member [STL/CLR]
- operator>=(list) member [STL/CLR]
ms.assetid: a70c45c8-a257-4f6b-8434-b27ff6685bac
ms.openlocfilehash: b23bc3f53cc13338e09ee8a6171d3da3b0b75d67
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344511"
---
# <a name="list-stlclr"></a>list (STL/CLR)

このテンプレートクラスは、双方向アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナーを使用して、一連の `list` 要素を双方向のリンクリストとして管理します。各ノードには1つの要素が格納されます。

次の説明で、 `GValue` は、後者が参照型である場合を除き、 *値* と同じです。この場合、は `Value^` です。

## <a name="syntax"></a>構文

```cpp
template<typename Value>
    ref class list
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        Microsoft::VisualC::StlClr::IList<GValue>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*Value*<br/>
被制御シーケンス内の要素の型。

## <a name="requirements"></a>要件

**ヘッダー:**\<cliext/list>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型の定義|説明|
|---------------------|-----------------|
|[list::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[list::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[list::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[list::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[list::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリックインターフェイスの型。|
|[list::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリックインターフェイスの反復子の型。|
|[list::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリックインターフェイスの反転反復子の型。|
|[list::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリックインターフェイスの要素の型。|
|[list::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[list::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[list::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[list::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[list::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[list::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[list::back (STL/CLR)](#back)|最後の要素にアクセスします。|
|[list::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[list::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[list::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[list::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[list::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[list::front (STL/CLR)](#front)|最初の要素にアクセスします。|
|[list::insert (STL/CLR)](#insert)|指定した位置に要素を追加します。|
|[list::list (STL/CLR)](#list)|コンテナー オブジェクトを構築します。|
|[list::merge (STL/CLR)](#merge)|2 つの順序付けされた被制御シーケンスをマージします。|
|[list::pop_back (STL/CLR)](#pop_back)|最後の要素を削除します。|
|[list::pop_front (STL/CLR)](#pop_front)|最初の要素を削除します。|
|[list::push_back (STL/CLR)](#push_back)|新しい最後の要素を追加します。|
|[list::push_front (STL/CLR)](#push_front)|新しい最初の要素を追加します。|
|[list::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[list::remove (STL/CLR)](#remove)|指定した値を持つ要素を削除します。|
|[list::remove_if (STL/CLR)](#remove_if)|指定したテストに合格した要素を削除します。|
|[list::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[list::resize (STL/CLR)](#resize)|要素の数を変更します。|
|[list::reverse (STL/CLR)](#reverse)|被制御シーケンスを反転させます。|
|[list::size (STL/CLR)](#size)|要素の数をカウントします。|
|[list::sort (STL/CLR)](#sort)|被制御シーケンスを順序付けます。|
|[list::splice (STL/CLR)](#splice)|ノード間のリンクを再接合します。|
|[list::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[list::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|
|[list::unique (STL/CLR)](#unique)|指定されたテストに合格した隣接する要素を削除します。|

|プロパティ|説明|
|--------------|-----------------|
|[list::back_item (STL/CLR)](#back_item)|最後の要素にアクセスします。|
|[list::front_item (STL/CLR)](#front_item)|最初の要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[list::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[operator!= (list) (STL/CLR)](#op_neq)|オブジェクトが別のオブジェクトと等しくないかどうかを判断し `list` `list` ます。|
|[operator< (list) (STL/CLR)](#op_lt)|`list`オブジェクトが別のオブジェクトより小さいかどうかを判断し `list` ます。|
|[operator<= (list) (STL/CLR)](#op_lteq)|オブジェクトが別のオブジェクト以下かどうかを判断し `list` `list` ます。|
|[operator = = (list) (STL/CLR)](#op_eq)|オブジェクトが別のオブジェクトと等しいかどうかを判断し `list` `list` ます。|
|[operator> (list) (STL/CLR)](#op_gt)|`list`オブジェクトが他のオブジェクトより大きいかどうかを判断し `list` ます。|
|[operator>= (list) (STL/CLR)](#op_gteq)|オブジェクトが別のオブジェクト以上かどうかを判断し `list` `list` ます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|<xref:System.Collections.IEnumerable>|要素を順番に処理します。|
|<xref:System.Collections.ICollection>|要素のグループを維持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番に処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|
|IList\<Value>|ジェネリックコンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、双方向リンクリスト内の個々のノードとして制御するシーケンスのストレージを割り当て、解放します。 ノード間のリンクを変更して要素を再配置します。1つのノードのコンテンツを別のノードにコピーすることはできません。 つまり、要素を自由に挿入および削除できます。 そのため、リストは、テンプレートクラス [キュー (stl/clr)](../dotnet/queue-stl-clr.md) またはテンプレートクラス [スタック (stl/clr)](../dotnet/stack-stl-clr.md)の基になるコンテナーの候補として適しています。

`list`オブジェクトは双方向反復子をサポートします。したがって、被制御シーケンス内の要素を指定する反復子によって隣接する要素にステップインできます。 特別なヘッドノードは、 [list:: end (STL/CLR)](#end)によって返される反復子に対応 `()` します。 この反復子をデクリメントして、被制御シーケンスの最後の要素 (存在する場合) に移動することができます。 リスト反復子をインクリメントしてヘッドノードに移動することができ、これはと等しいと比較され `end()` ます。 ただし、によって返される反復子を逆参照することはできません `end()` 。

ランダムアクセス反復子を必要とする数値の位置を指定して、リスト要素を直接参照することはできないことに注意してください。 そのため、リストは、テンプレートクラス [priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)の基になるコンテナーとして使用 *できません*。

リスト反復子は、関連付けられたリストノードへのハンドルを格納します。このノードは、関連付けられたコンテナーへのハンドルを格納します。 反復子は、関連付けられているコンテナーオブジェクトと共にのみ使用できます。 リストの反復子は、関連付けられたリストノードがリストに関連付けられている限り有効です。 さらに、有効な反復子は dereferencable です。これを使用すると、に指定した要素の値にアクセスしたり、変更したりすることができ `end()` ます。

要素を消去または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナーを破棄すると、すべての要素が消去されます。 したがって、要素の型が ref クラスであるコンテナーは、コンテナーの直後要素が存在しないことを保証します。 ただし、ハンドルのコンテナーが要素を破棄し *ない* ことに注意してください。

## <a name="members"></a>メンバー

## <a name="listassign-stlclr"></a><a name="assign"></a> list:: assign (STL/CLR)

すべての要素を置換します。

### <a name="syntax"></a>構文

```cpp
void assign(size_type count, value_type val);
template<typename InIt>
    void assign(InIt first, InIt last);
void assign(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>パラメーター

*count*<br/>
挿入する要素の数。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*そうです*<br/>
挿入する列挙体。

*val*<br/>
挿入する要素の値。

### <a name="remarks"></a>解説

最初のメンバー関数は、被制御シーケンスを、値 *val* の *count* 要素の繰り返しで置き換えます。 このメソッドを使用して、すべての要素が同じ値を持つコンテナーを塗りつぶします。

`InIt`が整数型の場合、2番目のメンバー関数はと同じように動作し `assign((size_type)first, (value_type)last)` ます。 それ以外の場合は、被制御シーケンスをシーケンス [ `first` ,) で置き換え `last` ます。 このメソッドを使用して、被制御シーケンスを別のシーケンスにコピーします。

3番目のメンバー関数は、被制御シーケンスを列挙子 *権限* によって指定されたシーケンスに置き換えます。 このメソッドを使用して、被制御シーケンスを列挙子によって記述されたシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_list_assign.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // assign a repetition of values
    cliext::list<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an iterator range
    cliext::list<wchar_t>::iterator it = c1.end();
    c2.assign(c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign an enumeration
    c2.assign(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
x x x x x x
a b
a b c
```

## <a name="listback-stlclr"></a><a name="back"></a> list:: back (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference back();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最後の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_list_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

    // alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back() = c
a b x
```

## <a name="listback_item-stlclr"></a><a name="back_item"></a> list:: back_item (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type back_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最後の要素にアクセスします。この要素は、空にすることはできません。 このメソッドは、最後の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_list_back_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

    // alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
back_item = c
a b x
```

## <a name="listbegin-stlclr"></a><a name="begin"></a> list:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定するランダムアクセス反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_list_begin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("*begin() = {0}", *it);
    System::Console::WriteLine("*++begin() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*begin() = a
*++begin() = b
x y c
```

## <a name="listclear-stlclr"></a><a name="clear"></a> list:: clear (STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

このメンバー関数は、list:: [erase](#erase) (stl/clr) list:: begin (stl/clr) list: `(` [](#begin) `(),` [: end (stl/](#end)clr) を実際に呼び出し `())` ます。 このメソッドを使用して、被制御シーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_list_clear.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0}", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');

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

## <a name="listconst_iterator-stlclr"></a><a name="const_iterator"></a> list:: const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T2` 被制御シーケンスの定数ランダムアクセス反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_list_const_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reference-stlclr"></a><a name="const_reference"></a> list:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_list_const_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::list<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a> list:: const_reverse_iterator (STL/CLR)

被制御シーケンスの定数反転反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T4` 被制御シーケンスの定数反転反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_list_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::list<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listdifference_type-stlclr"></a><a name="difference_type"></a> list::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、署名された要素の数を表します。

### <a name="example"></a>例

```cpp
// cliext_list_difference_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::difference_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.end();
        it != c1.begin(); --it) --diff;
    System::Console::WriteLine("begin()-end() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
begin()-end() = -3
```

## <a name="listempty-stlclr"></a><a name="empty"></a> list:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 [List:: size (STL/CLR)](#size)に相当 `() == 0` します。 このメソッドを使用して、リストが空かどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_empty.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

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

## <a name="listend-stlclr"></a><a name="end"></a> list:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示すランダムアクセス反復子を返します。 このメソッドを使用して、被制御シーケンスの末尾を指定する反復子を取得します。被制御シーケンスの長さが変更されている場合、その状態は変わりません。

### <a name="example"></a>例

```cpp
// cliext_list_end.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    cliext::list<wchar_t>::iterator it = c1.end();
    --it;
    System::Console::WriteLine("*-- --end() = {0}", *--it);
    System::Console::WriteLine("*--end() = {0}", *++it);

    // alter first two items and reinspect
    *--it = L'x';
    *++it = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --end() = b
*--end() = c
a x y
```

## <a name="listerase-stlclr"></a><a name="erase"></a> list:: erase (STL/CLR)

指定した位置にある要素を削除します。

### <a name="syntax"></a>構文

```cpp
iterator erase(iterator where);
iterator erase(iterator first, iterator last);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
消去する範囲の先頭。

*last*<br/>
消去する範囲の末尾。

*where*<br/>
消去する要素。

### <a name="remarks"></a>解説

最初のメンバー関数は、によって示さ *れる* 被制御シーケンスの要素を削除します。 このメソッドを使用して、1つの要素を削除します。

2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 これを使用して、0個以上の連続する要素を削除します。

どちらのメンバー関数も、削除された要素の後に残った最初の要素を指定する反復子を返します。そのような要素が存在しない場合は、 [list:: end (STL/CLR)](#end)を返し `()` ます。

要素が消去されるときに、要素のコピー数は、消去の終了位置とシーケンスの一番近い方の要素の数で線形になります。 (シーケンスの両端で1つ以上の要素を消去すると、要素のコピーは行われません)。

### <a name="example"></a>例

```cpp
// cliext_list_erase.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase an element and reinspect
    System::Console::WriteLine("erase(begin()) = {0}",
        *c1.erase(c1.begin()));

    // add elements and display " b c d e"
    c1.push_back(L'd');
    c1.push_back(L'e');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // erase all but end
    cliext::list<wchar_t>::iterator it = c1.end();
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

## <a name="listfront-stlclr"></a><a name="front"></a> list:: front (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference front();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素への参照を返します。この要素は、空にすることはできません。 これは、最初の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_list_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

    // alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front() = a
x b c
```

## <a name="listfront_item-stlclr"></a><a name="front_item"></a> list:: front_item (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type front_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最初の要素にアクセスします。この要素は、空にすることはできません。 これは、最初の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_list_front_item.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

    // alter first item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
front_item = a
x b c
```

## <a name="listgeneric_container-stlclr"></a><a name="generic_container"></a> list:: generic_container (STL/CLR)

コンテナーのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    IList<generic_value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_list_generic_container.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->insert(gc1->end(), L'd');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push_back(L'e');

    System::Collections::IEnumerator^ enum1 =
        gc1->GetEnumerator();
    while (enum1->MoveNext())
        System::Console::Write("{0} ", enum1->Current);
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

## <a name="listgeneric_iterator-stlclr"></a><a name="generic_iterator"></a> list:: generic_iterator (STL/CLR)

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
// cliext_list_generic_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a> list:: generic_reverse_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する逆順反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseBidirectionalIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反転反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_list_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c c
```

## <a name="listgeneric_value-stlclr"></a><a name="generic_value"></a> list:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、 `GValue` このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_list_generic_value.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::list<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::list<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::list<wchar_t>::generic_value gcval = *gcit;
    *++gcit = gcval;
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a a c
```

## <a name="listinsert-stlclr"></a><a name="insert"></a> list:: insert (STL/CLR)

指定した位置に要素を追加します。

### <a name="syntax"></a>構文

```cpp
iterator insert(iterator where, value_type val);
void insert(iterator where, size_type count, value_type val);
template<typename InIt>
    void insert(iterator where, InIt first, InIt last);
void insert(iterator where,
    System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>パラメーター

*count*<br/>
挿入する要素の数。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*そうです*<br/>
挿入する列挙体。

*val*<br/>
挿入する要素の値。

*where*<br/>
コンテナー内のの前に挿入する場所。

### <a name="remarks"></a>解説

各メンバー関数は、被制御シーケンス内の *where* が指す要素の前に、残りのオペランドによって指定されたシーケンスを挿入します。

1つ目のメンバー関数は、値 *val* を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 反復子によって指定された場所の前に1つの要素を挿入する場合に使用します。

2番目のメンバー関数は、値 *val* の *count* 要素の繰り返しを挿入します。 これを使用して、同じ値のすべてのコピーである0個以上の連続する要素を挿入します。

`InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合は、シーケンス [ `first` ,) を挿入 `last` します。 このメソッドを使用して、別のシーケンスからコピーされた0個以上の連続する要素を挿入します。

4番目のメンバー関数は、 *右側* に指定されたシーケンスを挿入します。 このメソッドを使用して、列挙子によって記述されたシーケンスを挿入します。

1つの要素を挿入する場合、要素のコピー数は、挿入ポイントとそれに近いシーケンスの末尾との間の要素の数で線形になります。 (シーケンスの両端に1つ以上の要素を挿入する場合、要素のコピーは行われません)。 `InIt` が入力反復子の場合、3番目のメンバー関数は、シーケンス内の各要素に対して1つの挿入を効果的に実行します。 それ以外の場合、要素を挿入するときに、 `N` 要素のコピーの数には、 `N` 挿入ポイントとそれに近いシーケンスの末尾との間の要素数が加算されます。

### <a name="example"></a>例

```cpp
// cliext_list_insert.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using iterator
    cliext::list<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a repetition of values
    cliext::list<wchar_t> c2;
    c2.insert(c2.begin(), 2, L'y');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an iterator range
    it = c1.end();
    c2.insert(c2.end(), c1.begin(), --it);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert an enumeration
    c2.insert(c2.begin(),   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c1);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using index
    it = c2.begin();
    ++it, ++it, ++it;
    c2.insert(it, L'z');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
a b c
insert(begin()+1, L'x') = x
a x b c
y y
y y a x b
a x b c y y a x b
```

## <a name="listiterator-stlclr"></a><a name="iterator"></a> list:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、 `T1` 被制御シーケンスのランダムアクセス反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_list_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();

    // alter first element and redisplay
    it = c1.begin();
    *it = L'x';
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
x b c
```

## <a name="listlist-stlclr"></a><a name="list"></a> list:: list (STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
list();
list(list<Value>% right);
list(list<Value>^ right);
explicit list(size_type count);
list(size_type count, value_type val);
template<typename InIt>
    list(InIt first, InIt last);
list(System::Collections::Generic::IEnumerable<Value>^ right);
```

#### <a name="parameters"></a>パラメーター

*count*<br/>
挿入する要素の数。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*そうです*<br/>
挿入するオブジェクトまたは範囲。

*val*<br/>
挿入する要素の値。

### <a name="remarks"></a>解説

コンストラクター:

`list();`

要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`list(list<Value>% right);`

シーケンス [,) を使用して被制御シーケンスを初期化し `right.begin()` `right.end()` ます。 これを使用して、リストオブジェクト *権限* によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。

コンストラクター:

`list(list<Value>^ right);`

シーケンス [,) を使用して被制御シーケンスを初期化し `right->begin()` `right->end()` ます。 これを使用して、ハンドルが *right* であるリストオブジェクトによって制御されるシーケンスのコピーである、最初の被制御シーケンスを指定します。

コンストラクター:

`explicit list(size_type count);`

値を持つ *カウント* 要素を使用して被制御シーケンスを初期化し `value_type()` ます。 このメソッドを使用して、すべての要素に既定値が設定されたコンテナーにデータを格納します。

コンストラクター:

`list(size_type count, value_type val);`

値 *val* を持つ *カウント* 要素を使用して被制御シーケンスを初期化します。 このメソッドを使用して、すべての要素が同じ値を持つコンテナーを塗りつぶします。

コンストラクター:

`template<typename InIt>`

`list(InIt first, InIt last);`

シーケンス [,) を使用して被制御シーケンスを初期化し `first` `last` ます。 このメソッドを使用して、被制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`list(System::Collections::Generic::IEnumerable<Value>^ right);`

列挙子 *権限* によって指定されたシーケンスを使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙子によって記述された別のシーケンスのコピーとして作成します。

### <a name="example"></a>例

```cpp
// cliext_list_construct.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    // construct with a repetition of default values
    cliext::list<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // construct with a repetition of values
    cliext::list<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    cliext::list<wchar_t>::iterator it = c3.end();
    cliext::list<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    cliext::list<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    cliext::list<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    cliext::list<wchar_t> c8(%c3);
    for each (wchar_t elem in c8)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
0 0 0
x x x x x x
x x x x x
x x x x x x
x x x x x x
x x x x x x
```

## <a name="listmerge-stlclr"></a><a name="merge"></a> list:: merge (STL/CLR)

2 つの順序付けされた被制御シーケンスをマージします。

### <a name="syntax"></a>構文

```cpp
void merge(list<Value>% right);
template<typename Pred2>
    void merge(list<Value>% right, Pred2 pred);
```

#### <a name="parameters"></a>パラメーター

*pred*<br/>
要素のペアの比較子。

*そうです*<br/>
マージするコンテナー。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、 *right* によって制御されるシーケンスからすべての要素を削除し、被制御シーケンスに挿入します。 2つのシーケンスは、どちらの順序でも、値を小さくすることはできませ `operator<` ん。 結果のシーケンスもによって並べ替えられ `operator<` ます。 このメンバー関数を使用すると、値が増加する2つのシーケンスを、値の増加もするシーケンスにマージできます。

2番目のメンバー関数は、最初と同じように動作しますが、 `pred`  --  `pred(X, Y)` シーケンス内の要素の後に続くすべての要素について、シーケンスが false である必要があり `X` `Y` ます。 これを使用して、指定した述語関数またはデリゲートによって順序付けられた2つのシーケンスをマージします。

どちらの関数も安定したマージを実行します。元の被制御シーケンスのいずれかの要素のペアは、結果の被制御シーケンスでは逆になります。 また、 `X` 結果として `Y` 得られる被制御シーケンス内の要素とのペアが等価の順序付けを持つ場合 ( `!(X < Y) && !(X < Y)` 元の被制御シーケンスの要素は、 *右辺* で制御されるシーケンスの要素の前にあります)。

### <a name="example"></a>例

```cpp
// cliext_list_merge.cpp
// compile with: /clr
#include <cliext/list>

typedef cliext::list<wchar_t> Mylist;
int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'c');
    c1.push_back(L'e');

    // display initial contents " a c e"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    cliext::list<wchar_t> c2;
    c2.push_back(L'b');
    c2.push_back(L'd');
    c2.push_back(L'f');

    // display initial contents " b d f"
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // merge and display
    cliext::list<wchar_t> c3(c1);
    c3.merge(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());

    // sort descending, merge descending, and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    c3.merge(c1, cliext::greater<wchar_t>());
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    return (0);
    }
```

```Output
a c e
b d f
a b c d e f
c2.size() = 0
e c a
f e d c b a
f e e d c c b a a
c1.size() = 0
```

## <a name="listoperator-stlclr"></a><a name="op_as"></a> list:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```
list<Value>% operator=(list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 このメソッドを使用して、被制御シーケンスを *右側* の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_list_operator_as.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2 = c1;
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="listpop_back-stlclr"></a><a name="pop_back"></a> list::p op_back (STL/CLR)

最後の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop_back();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素を削除します。この要素は空にすることはできません。 これを使用して、リストを1つ前の要素で短くします。

### <a name="example"></a>例

```cpp
// cliext_list_pop_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_back();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b
```

## <a name="listpop_front-stlclr"></a><a name="pop_front"></a> list::p op_front (STL/CLR)

最初の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop_front();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素を削除します。この要素は空でない必要があります。 このメソッドを使用して、前の1つの要素でリストを短縮します。

### <a name="example"></a>例

```cpp
// cliext_list_pop_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop_front();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
b c
```

## <a name="listpush_back-stlclr"></a><a name="push_back"></a> list::p ush_back (STL/CLR)

新しい最後の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、 `val` 被制御シーケンスの末尾に値を持つ要素を挿入します。 このメソッドを使用して、リストに別の要素を追加します。

### <a name="example"></a>例

```cpp
// cliext_list_push_back.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="listpush_front-stlclr"></a><a name="push_front"></a> list::p ush_front (STL/CLR)

新しい最初の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push_front(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、 `val` 被制御シーケンスの先頭に値を持つ要素を挿入します。 このメソッドを使用して、リストに別の要素の前に付加します。

### <a name="example"></a>例

```cpp
// cliext_list_push_front.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_front(L'a');
    c1.push_front(L'b');
    c1.push_front(L'c');

    // display contents " c b a"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="listrbegin-stlclr"></a><a name="rbegin"></a> list:: rbegin (STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素、または空のシーケンスの先頭の次の位置を指定する反転反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_list_rbegin.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    System::Console::WriteLine("*rbegin() = {0}", *rit);
    System::Console::WriteLine("*++rbegin() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*rbegin() = c
*++rbegin() = b
a y x
```

## <a name="listreference-stlclr"></a><a name="reference"></a> list:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_list_reference.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::list<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

    // modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::list<wchar_t>::reference ref = *it;

        ref += (wchar_t)(L'A' - L'a');
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
A B C
```

## <a name="listremove-stlclr"></a><a name="remove"></a> list:: remove (STL/CLR)

指定した値を持つ要素を削除します。

### <a name="syntax"></a>構文

```cpp
void remove(value_type val);
```

#### <a name="parameters"></a>パラメーター

*val*<br/>
削除する要素の値。

### <a name="remarks"></a>解説

このメンバー関数は、が true (存在する場合) の被制御シーケンス内の要素を削除し `((System::Object^)val)->Equals((System::Object^)x)` ます。 このメソッドを使用して、指定した値を持つ任意の要素を消去します。

### <a name="example"></a>例

```cpp
// cliext_list_remove.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove(L'A');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove(L'b');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a c
```

## <a name="listremove_if-stlclr"></a><a name="remove_if"></a> list:: remove_if (STL/CLR)

指定したテストに合格した要素を削除します。

### <a name="syntax"></a>構文

```cpp
template<typename Pred1>
    void remove_if(Pred1 pred);
```

#### <a name="parameters"></a>パラメーター

*pred*<br/>
削除する要素をテストします。

### <a name="remarks"></a>解説

このメンバー関数は、が true であるすべての要素を被制御シーケンスから削除し `X` `pred(X)` ます。 関数またはデリゲートとして指定した条件を満たすすべての要素を削除するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_list_remove_if.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b b b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // fail to remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::equal_to<wchar_t> >(
        cliext::equal_to<wchar_t>(), L'd'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // remove and redisplay
    c1.remove_if(cliext::binder2nd<cliext::not_equal_to<wchar_t> >(
        cliext::not_equal_to<wchar_t>(), L'b'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b b b c
a b b b c
b b b
```

## <a name="listrend-stlclr"></a><a name="rend"></a> list:: rend (STL/CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの先頭を越えた位置を示す反転反復子を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_list_rend.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::list<wchar_t>::reverse_iterator rit = c1.rend();
    --rit;
    System::Console::WriteLine("*-- --rend() = {0}", *--rit);
    System::Console::WriteLine("*--rend() = {0}", *++rit);

    // alter first two items and reinspect
    *--rit = L'x';
    *++rit = L'y';
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
*-- --rend() = b
*--rend() = a
y x c
```

## <a name="listresize-stlclr"></a><a name="resize"></a> list:: resize (STL/CLR)

要素の数を変更します。

### <a name="syntax"></a>構文

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>パラメーター

*new_size*<br/>
被制御シーケンスの新しいサイズ。

*val*<br/>
埋め込み要素の値。

### <a name="remarks"></a>解説

メンバー関数は、 [list:: size (STL/CLR)](#size) `()` その後が *new_size* を返すことを保証します。 被制御シーケンスを長くする必要がある場合、最初のメンバー関数は値を持つ要素を追加し、 `value_type()` 2 番目のメンバー関数は値 *val* を持つ要素を追加します。 被制御シーケンスを短くするために、両方のメンバー関数は、最後の要素[リスト:: size (STL/CLR)](#size)の時刻を効果的に消去し `() -` `new_size` ます。 このメソッドを使用すると、現在の被制御シーケンスのトリミングまたは埋め込みによって、被制御シーケンスのサイズが *new_size* になるようにすることができます。

### <a name="example"></a>例

```cpp
// cliext_list_resize.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
// construct an empty container and pad with default values
    cliext::list<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());
    c1.resize(4);
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // resize to empty
    c1.resize(0);
    System::Console::WriteLine("size() = {0}", c1.size());

    // resize and pad
    c1.resize(5, L'x');
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
0 0 0 0
size() = 0
x x x x x
```

## <a name="listreverse-stlclr"></a><a name="reverse"></a> list:: reverse (STL/CLR)

被制御シーケンスを反転させます。

### <a name="syntax"></a>構文

```cpp
void reverse();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンス内のすべての要素の順序を逆にします。 要素の一覧を反映するために使用します。

### <a name="example"></a>例

```cpp
// cliext_list_reverse.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // reverse and redisplay
    c1.reverse();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
```

## <a name="listreverse_iterator-stlclr"></a><a name="reverse_iterator"></a> list:: reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T3` 被制御シーケンスの反転反復子として使用できる指定されていない型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_list_reverse_iterator.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::list<wchar_t>::reverse_iterator rit = c1.rbegin();
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();

    // alter first element and redisplay
    rit = c1.rbegin();
    *rit = L'x';
    for (; rit != c1.rend(); ++rit)
        System::Console::Write("{0} ", *rit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
x b a
```

## <a name="listsize-stlclr"></a><a name="size"></a> list:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスにゼロ以外のサイズがあるかどうかは、「 [list:: empty (STL/CLR)](#empty)」を参照してください `()` 。

### <a name="example"></a>例

```cpp
// cliext_list_size.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // clear the container and reinspect
    c1.clear();
    System::Console::WriteLine("size() = {0} after clearing", c1.size());

    // add elements and clear again
    c1.push_back(L'a');
    c1.push_back(L'b');
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

## <a name="listsize_type-stlclr"></a><a name="size_type"></a> list:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_list_size_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::list<wchar_t>::size_type diff = 0;
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="listsort-stlclr"></a><a name="sort"></a> list:: sort (STL/CLR)

被制御シーケンスを順序付けます。

### <a name="syntax"></a>構文

```cpp
void sort();
template<typename Pred2>
    void sort(Pred2 pred);
```

#### <a name="parameters"></a>パラメーター

*pred*<br/>
要素のペアの比較子。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、被制御シーケンス内の要素を再配置して、 `operator<` シーケンス処理の進行に応じて値が減少しないようにします。 シーケンスを昇順に並べ替えるには、このメンバー関数を使用します。

2番目のメンバー関数は、最初と同じように動作しますが、 `pred`  --  `pred(X, Y)` 結果のシーケンスの要素の後に続く要素については、シーケンスの順序が false である点が異なり `X` `Y` ます。 このメソッドは、述語関数またはデリゲートによって指定された順序でシーケンスを並べ替えるために使用します。

どちらの関数も安定した並べ替えを実行します。元の被制御シーケンス内の要素のペアは、結果の被制御シーケンスでは逆になります。

### <a name="example"></a>例

```cpp
// cliext_list_sort.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort descending and redisplay
    c1.sort(cliext::greater<wchar_t>());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // sort ascending and redisplay
    c1.sort();
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
c b a
a b c
```

## <a name="listsplice-stlclr"></a><a name="splice"></a> list:: スプライス (STL/CLR)

ノード間のリンクを再合成します。

### <a name="syntax"></a>構文

```cpp
void splice(iterator where, list<Value>% right);
void splice(iterator where, list<Value>% right,
    iterator first);
void splice(iterator where, list<Value>% right,
    iterator first, iterator last);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
スプライスの範囲の先頭。

*last*<br/>
スプライスの範囲の末尾。

*そうです*<br/>
スプライスするコンテナー。

*where*<br/>
コンテナー内のスプライスの前の場所。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、 *where* でポイントされた被制御シーケンス内の要素の前に、 *right* で制御されるシーケンスを挿入します。 また、すべての要素を *右* から削除します。 ( `%right` はと等しくない必要があり **`this`** ます)。このメソッドを使用して、すべてのリストを別のリストにスプライスします。

2番目のメンバー関数は、 *right* によって制御されるシーケンス内の *最初* のが指す要素を削除し、 *where* によって示される被制御シーケンス内の要素の前に挿入します。 (If `where` `==``first` `||` `where``== ++first`では、変更は行われません)。このメソッドを使用して、あるリストの1つの要素を別のリストにスプライスします。

3番目のメンバー関数は、where でポイントされた `first` `last` 被制御シーケンス内の要素の直前に、[,) によって指定されたサブ *範囲* を挿入します。 また、 *right* によって制御されるシーケンスから元のサブ範囲も削除されます。 (の場合 `right == this` 、範囲 [,) には、が指す要素を含めることはでき `first` `last` ません。 このメソッドを使用して、0個以上の要素のサブシーケンスを1つのリストから別のリストにスプライスします。

### <a name="example"></a>例

```cpp
// cliext_list_splice.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // splice to a new list
    cliext::list<wchar_t> c2;
    c2.splice(c2.begin(), c1);
    System::Console::WriteLine("c1.size() = {0}", c1.size());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return one element
    c1.splice(c1.end(), c2, c2.begin());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // return remaining elements
    c1.splice(c1.begin(), c2, c2.begin(), c2.end());
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("c2.size() = {0}", c2.size());
    return (0);
    }
```

```Output
a b c
c1.size() = 0
a b c
a
b c
b c a
c2.size() = 0
```

## <a name="listswap-stlclr"></a><a name="swap"></a> list:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、との間で被制御シーケンスを交換し **`*this`** ます。  この処理は一定時間に実行され、例外はスローされません。 2つのコンテナーの内容を簡単に交換する方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_list_swap.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::list<wchar_t> c2(5, L'x');
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
x x x x x
x x x x x
a b c
```

## <a name="listto_array-stlclr"></a><a name="to_array"></a> list:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_list_to_array.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push_back(L'd');
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

## <a name="listunique-stlclr"></a><a name="unique"></a> list:: unique (STL/CLR)

指定されたテストに合格した隣接する要素を削除します。

### <a name="syntax"></a>構文

```cpp
void unique();
template<typename Pred2>
    void unique(Pred2 pred);
```

#### <a name="parameters"></a>パラメーター

*pred*<br/>
要素のペアの比較子。

### <a name="remarks"></a>解説

1つ目のメンバー関数は、前の要素と等しいかどうかを比較するすべての要素を被制御シーケンス (消去) から削除します。要素がの前にある場合は `X` `Y` `X == Y` 、メンバー関数はを削除し `Y` ます。 これを使用すると、隣接する要素のすべてのサブシーケンスのうち、等しいものを比較して1つを除くすべてのコピーが削除されます。 [List:: sort (STL/CLR)](#sort)を呼び出すなどして被制御シーケンスが順序付けされている場合、 `()` メンバー関数は、一意の値を持つ要素のみを残します。 (ターミナル メソッドという名前なのはそのためです)。

2番目のメンバー関数は、1番目のメンバー関数と同じように動作しますが、 `Y` の要素の後にある各要素が削除される点が異なり `X` `pred(X, Y)` ます。 これを使用して、指定した述語関数またはデリゲートを満たす隣接する要素のすべてのサブシーケンスの1つを除くすべてのコピーを削除します。 を呼び出した場合など、被制御シーケンスが順序付けされている場合、 `sort(pred)` メンバー関数は、他の要素と等価な順序付けを持たない要素だけを残します。

### <a name="example"></a>例

```cpp
// cliext_list_unique.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique
    cliext::list<wchar_t> c2(c1);
    c2.unique();
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display contents after unique(not_equal_to)
    c2 = c1;
    c2.unique(cliext::not_equal_to<wchar_t>());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a a b c
a b c
a a
```

## <a name="listvalue_type-stlclr"></a><a name="value_type"></a> list:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター *値* のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_list_value_type.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using value_type
    for (cliext::list<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::list<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-list-stlclr"></a><a name="op_neq"></a> operator! = (list) (STL/CLR)

リストが等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator!=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left == right)` ます。 このメソッドを使用して、2つのリストが要素ごとに比較されるときに、 *left* が *right* と同じ順序で並んでいないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_ne.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-list-stlclr"></a><a name="op_lt"></a> operator &lt; (list) (STL/CLR)

比較より小さいリスト。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、が true である場合にも true を返し `i` `!(right[i] < left[i])` `left[i] < right[i]` ます。 それ以外の場合は、このメソッドを `left->size() < right->size()` 使用して、2つのリストが要素で比較されるときに、 *left* が *right* の前に並べられているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_lt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorlt-list-stlclr"></a><a name="op_lteq"></a> operator &lt; = (list) (STL/CLR)

以下を比較します。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(right < left)` ます。 このメソッドを使用して、2つのリストが要素別に比較されるときに、 *right* の後に *left* が順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_le.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operator-list-stlclr"></a><a name="op_eq"></a> operator = = (list) (STL/CLR)

同じ比較を一覧表示します。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator==(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、 *左* と *右* で制御されるシーケンスの長さが同じで、各位置についてがである場合にのみ true を返し `i` `left[i] ==` `right[i]` ます。 このメソッドを使用して、2つのリストが要素によって比較されるときに、 *left* が *right* と同じ順序で並んでいるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_eq.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-list-stlclr"></a><a name="op_gt"></a> operator &gt; (list) (STL/CLR)

比較よりも大きいリストです。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `right` `<` `left` ます。 このメソッドを使用して、2つのリストが要素別に比較されたときに、 *left* が *right* の後に並べられているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_gt.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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

## <a name="operatorgt-list-stlclr"></a><a name="op_gteq"></a> operator &gt; = (list) (STL/CLR)

以上の比較を一覧表示します。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>=(list<Value>% left,
        list<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left` `<` `right)` ます。 このメソッドを使用して、2つのリストが要素別に比較されるときに、 *left* が *right* の前に順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_list_operator_ge.cpp
// compile with: /clr
#include <cliext/list>

int main()
    {
    cliext::list<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::list<wchar_t> c2;
    c2.push_back(L'a');
    c2.push_back(L'b');
    c2.push_back(L'd');

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
