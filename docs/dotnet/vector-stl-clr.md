---
title: vector (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::vector
- cliext::vector::assign
- cliext::vector::at
- cliext::vector::back
- cliext::vector::back_item
- cliext::vector::begin
- cliext::vector::capacity
- cliext::vector::clear
- cliext::vector::const_iterator
- cliext::vector::const_reference
- cliext::vector::const_reverse_iterator
- cliext::vector::difference_type
- cliext::vector::empty
- cliext::vector::end
- cliext::vector::erase
- cliext::vector::front
- cliext::vector::front_item
- cliext::vector::generic_container
- cliext::vector::generic_iterator
- cliext::vector::generic_reverse_iterator
- cliext::vector::generic_value
- cliext::vector::insert
- cliext::vector::iterator
- cliext::vector::operator=
- cliext::vector::operator
- cliext::vector::pop_back
- cliext::vector::push_back
- cliext::vector::rbegin
- cliext::vector::reference
- cliext::vector::rend
- cliext::vector::reserve
- cliext::vector::resize
- cliext::vector::reverse_iterator
- cliext::vector::size
- cliext::vector::size_type
- cliext::vector::swap
- cliext::vector::to_array
- cliext::vector::value_type
- cliext::vector::vector
helpviewer_keywords:
- vector class [STL/CLR]
- <cliext/vector> header [STL/CLR]
- <vector> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> (vector) member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- capacity member [STL/CLR]
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
- operator= member [STL/CLR]
- operator member [STL/CLR]
- pop_back member [STL/CLR]
- push_back member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- reserve member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- vector member [STL/CLR]
ms.assetid: f90060d5-097a-4e9d-9a26-a634b5b9c6c2
ms.openlocfilehash: c6a001797e90bd7381358abb16612926442e8d9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371819"
---
# <a name="vector-stlclr"></a>vector (STL/CLR)

テンプレート クラスは、ランダム アクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナー`vector`を使用して、連続したストレージ・ブロックとしてエレメントのシーケンスを管理します。 ブロックは、オンデマンドで拡張される配列として実装されます。

以下の説明では、`GValue`後者が ref 型でない限り *、値*と同じです。 `Value^`

## <a name="syntax"></a>構文

```cpp
template<typename Value>
    ref class vector
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IVector<GValue>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*Value*<br/>
被制御シーケンス内の要素の型。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<クリオト/ベクトル>

**名前空間:** クエクスキ

## <a name="declarations"></a>宣言

|型定義|説明|
|---------------------|-----------------|
|[vector::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[vector::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[vector::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[vector::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[vector::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリック インターフェイスの型。|
|[vector::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリック インターフェイスの反復器の型。|
|[vector::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリック インターフェイスの逆反復器の型。|
|[vector::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリック インターフェイスの要素の型。|
|[vector::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[vector::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[vector::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[vector::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[vector::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[vector::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[vector::at (STL/CLR)](#at)|指定した位置にある要素にアクセスします。|
|[vector::back (STL/CLR)](#back)|最後の要素にアクセスします。|
|[vector::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[vector::capacity (STL/CLR)](#capacity)|コンテナーに割り当てられたストレージの容量を報告します。|
|[vector::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[vector::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[vector::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[vector::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[vector::front (STL/CLR)](#front)|最初の要素にアクセスします。|
|[vector::insert (STL/CLR)](#insert)|指定した位置に要素を追加します。|
|[vector::pop_back (STL/CLR)](#pop_back)|最後の要素を削除します。|
|[vector::push_back (STL/CLR)](#push_back)|新しい最後の要素を追加します。|
|[vector::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[vector::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[vector::reserve (STL/CLR)](#reserve)|コンテナーの最小の拡張容量を確保します。|
|[vector::resize (STL/CLR)](#resize)|要素の数を変更します。|
|[vector::size (STL/CLR)](#size)|要素の数をカウントします。|
|[vector::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[vector::to_array (STL/CLR)](#to_array)|制御されたシーケンスを新しい配列にコピーします。|
|[vector::vector (STL/CLR)](#vector)|コンテナー オブジェクトを構築します。|

|プロパティ|説明|
|--------------|-----------------|
|[vector::back_item (STL/CLR)](#back_item)|最後の要素にアクセスします。|
|[vector::front_item (STL/CLR)](#front_item)|最初の要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[vector::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[vector::operator(STL/CLR)](#op)|指定した位置にある要素にアクセスします。|
|[演算子!= (ベクター) (STL/CLR)](#op_neq)|オブジェクトが別`vector``vector`のオブジェクトと等しくないかどうかを判断します。|
|[演算子< (ベクトル) (STL/CLR)](#op_lt)|オブジェクトが別`vector``vector`のオブジェクトより小さいかどうかを判断します。|
|[演算子<= (ベクトル) (STL/CLR)](#op_lteq)|オブジェクトが別`vector``vector`のオブジェクト以下かどうかを判断します。|
|[演算子==(ベクトル) (STL/CLR)](#op_eq)|オブジェクトが別`vector``vector`のオブジェクトと等しいかどうかを判断します。|
|[演算子> (ベクトル) (STL/CLR)](#op_gt)|オブジェクトが別`vector``vector`のオブジェクトより大きいかどうかを判断します。|
|[operator>= (vector) (STL/CLR)](#op_gteq)|オブジェクトが別`vector``vector`のオブジェクト以上かどうかを判断します。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製する。|
|<xref:System.Collections.IEnumerable>|要素を通してシーケンスします。|
|<xref:System.Collections.ICollection>|要素のグループを管理します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を通してシーケンスします。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを管理します。|
|<xref:System.Collections.Generic.IList%601>|型指定された要素の順序付けられたグループを維持します。|
|IVector<値\>|汎用コンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、必要に応じて増加する*Value*要素の格納された配列を介して、制御するシーケンスのストレージを割り当て、解放します。 成長は、新しい要素を追加するコストが一定の時間を償却するような方法で発生します。 つまり、制御シーケンスの長さが大きくなるにつれて、最後に要素を追加するコストは平均して増加しません。 したがって、ベクトルは、テンプレート クラス[スタック (STL/CLR)](../dotnet/stack-stl-clr.md)の基になるコンテナーの候補として適しています。

A`vector`はランダム アクセス反復子をサポートしており、最初の (前面) 要素の 0 から最後の (背面) 要素まで、数値`size() - 1`位置を指定して要素を直接参照できます。 また、ベクターがテンプレート クラス[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)の基になるコンテナーの候補であることを意味します。

ベクトル反復子は、指定した要素のバイアスと共に、関連するベクトル オブジェクトへのハンドルを格納します。 反復子は、関連付けられたコンテナー オブジェクトでのみ使用できます。 ベクトル要素のバイアスは、その位置と同じです。

要素の挿入または削除は、特定の位置に格納されている要素の値を変更できるため、反復子によって指定された値も変更できます。 (挿入の前に穴を作成したり、消去後に穴を埋めるために、コンテナは要素を上下にコピーする必要があります)。それにもかかわらず、ベクトル反復器は、そのバイアスが範囲`[0, size()]`内にある限り有効です。 さらに、有効な反復子は、バイアスが 等しくない限り、指定した要素値にアクセスしたり変更したりするために使用できます`size()`。

要素を削除または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナを破棄すると、すべての要素が消去されます。 したがって、要素型が ref クラスであるコンテナーは、コンテナーより長い要素が存在することを保証します。 ただし、ハンドルのコンテナーは要素を破棄しないことに注意してください。

## <a name="members"></a>メンバー

## <a name="vectorassign-stlclr"></a><a name="assign"></a>ベクトル::割り当て(STL/CLR)

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

*ヴァル*<br/>
挿入する要素の値。

### <a name="remarks"></a>解説

最初のメンバー関数は、制御されたシーケンスを value *val*の*カウント*要素の繰り返しに置き換えます。 この値を使用して、同じ値を持つ要素をすべてコンテナーに埋めます。

整数`InIt`型の場合、2 番目のメンバー関数は と同`assign((size_type)first, (value_type)last)`じように動作します。 それ以外の場合は、制御されたシーケンスがシーケンス`first`[ `last`, で置き換えられます。 これを使用して、制御されたシーケンスを別のシーケンスにコピーします。

3 番目のメンバー関数は、制御されたシーケンスを、列挙子*right*で指定されたシーケンスに置き換えます。 これを使用して、制御されたシーケンスを列挙子によって記述されたシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_vector_assign.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// assign a repetition of values
    cliext::vector<wchar_t> c2;
    c2.assign(6, L'x');
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign an iterator range
    c2.assign(c1.begin(), c1.end() - 1);
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

## <a name="vectorat-stlclr"></a><a name="at"></a>ベクトル::at (STL/CLR)

指定した位置にある要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>パラメーター

*pos*<br/>
アクセスする要素の位置。

### <a name="remarks"></a>解説

このメンバー関数は、 *pos*位置にある制御シーケンスの要素への参照を返します。位置がわかっている要素を読み書きするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_at.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using at
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// change an entry and redisplay
    c1.at(1) = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorback-stlclr"></a><a name="back"></a>ベクトル::バック(STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference back();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最後の要素への参照を返します。 最後の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorback_item-stlclr"></a><a name="back_item"></a>ベクトル::back_item (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type back_item;
```

### <a name="remarks"></a>解説

プロパティは、制御されたシーケンスの最後の要素にアクセスします。 最後の要素が存在することがわかっている場合に、最後の要素を読み書きするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_back_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorbegin-stlclr"></a><a name="begin"></a>ベクトル::開始 (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最初の要素、または空のシーケンスの末尾を越えた直後を指定するランダム アクセス反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_vector_begin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::iterator it = c1.begin();
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

## <a name="vectorcapacity-stlclr"></a><a name="capacity"></a>ベクトル::容量(STL/CLR)

コンテナーに割り当てられたストレージの容量を報告します。

### <a name="syntax"></a>構文

```cpp
size_type capacity();
```

### <a name="remarks"></a>解説

このメンバー関数は、制御されたシーケンスを保持するために現在割り当てられているストレージを[返](../dotnet/vector-size-stl-clr.md)`()`します。 これを使用して、コンテナーが、制御されたシーケンスの記憶域を再割り当てする前に、どの程度拡張できるかを決定します。

### <a name="example"></a>例

```cpp
// cliext_vector_capacity.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorclear-stlclr"></a><a name="clear"></a>ベクトル::クリア(STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

メンバー関数は効果的にベクターを呼び出します[::消去 (STL/CLR)](../dotnet/vector-erase-stl-clr.md) `(` [ベクター::開始 (STL/CLR)](../dotnet/vector-begin-stl-clr.md) `(),` [ベクトル::終了 (STL/CLR)](../dotnet/vector-end-stl-clr.md)`())`. これを使用して、制御されたシーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_vector_clear.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorconst_iterator-stlclr"></a><a name="const_iterator"></a>ベクトル::const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数ランダム`T2`アクセス反復器として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_const_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reference-stlclr"></a><a name="const_reference"></a>ベクトル::const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_const_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::vector<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>ベクトル::const_reverse_iterator (STL/CLR)

制御シーケンスの定数逆反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの定数逆`T4`反復器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::vector<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="vectordifference_type-stlclr"></a><a name="difference_type"></a>ベクトル::difference_型 (STL/CLR)

2 つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、符号付き要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_difference_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::difference_type diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

// compute negative difference
    diff = 0;
    for (cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorempty-stlclr"></a><a name="empty"></a>ベクトル::空 (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[ベクトル::サイズ(STL/CLR)と](../dotnet/vector-size-stl-clr.md)`() == 0`同等です。 ベクターが空であるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_empty.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorend-stlclr"></a><a name="end"></a>ベクトル::終了 (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの末尾を越えたところを指すランダム アクセス反復器を返します。 これを使用して被制御シーケンスの現在の (`current`) 末尾を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_vector_end.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last two items
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorerase-stlclr"></a><a name="erase"></a>ベクトル::消去(STL /CLR)

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
消去する範囲の終わり。

*where*<br/>
消去する要素。

### <a name="remarks"></a>解説

最初のメンバー関数は、 によって指される制御シーケンスの要素を*削除します。* 1 つの要素を削除する場合に使用します。

2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 この値を使用して、連続する要素を 0 個以上削除します。

両方のメンバー関数は、削除された要素を超えて残っている最初の要素を指定する反復子[を返](../dotnet/vector-end-stl-clr.md)`()`します。

要素を消去する場合、要素のコピー数は、消去の終了とシーケンスの終わり近くの要素の数で線形になります。 (シーケンスの両端で 1 つ以上の要素を削除しても、要素のコピーは発生しません)。

### <a name="example"></a>例

```cpp
// cliext_vector_erase.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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
    cliext::vector<wchar_t>::iterator it = c1.end();
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

## <a name="vectorfront-stlclr"></a><a name="front"></a>ベクトル::フロント(STL /CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference front();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最初の要素への参照を返します。 最初の要素が存在することがわかっている場合に、この要素を使用して読み書きします。

### <a name="example"></a>例

```cpp
// cliext_vector_front.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorfront_item-stlclr"></a><a name="front_item"></a>ベクトル::front_item (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type front_item;
```

### <a name="remarks"></a>解説

プロパティは、制御されたシーケンスの最初の要素にアクセスします。 最初の要素が存在することがわかっている場合に、この要素を使用して読み書きします。

### <a name="example"></a>例

```cpp
// cliext_vector_front_item.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorgeneric_container-stlclr"></a><a name="generic_container"></a>ベクトル::generic_container (STL/CLR)

コンテナーのジェネリック インターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    IVector<generic_value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_generic_container.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
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

## <a name="vectorgeneric_iterator-stlclr"></a><a name="generic_iterator"></a>ベクトル::generic_iterator (STL/CLR)

コンテナーのジェネリック インターフェイスで使用する反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value>
    generic_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスで使用できるジェネリック反復器を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_generic_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorgeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>ベクトル::generic_reverse_iterator (STL/CLR)

コンテナのジェネリック インターフェイスで使用するリバース反復器の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー クラスのジェネリック インターフェイスで使用できる汎用リバース 反復処理を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorgeneric_value-stlclr"></a><a name="generic_value"></a>ベクトル::generic_value (STL/CLR)

コンテナーのジェネリック インターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、このテンプレート コンテナー`GValue`クラスのジェネリック インターフェイスで使用する格納された要素の値を記述する型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_generic_value.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    cliext::vector<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify generic and display original
    cliext::vector<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::vector<wchar_t>::generic_value gcval = *gcit;
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

## <a name="vectorinsert-stlclr"></a><a name="insert"></a>ベクトル::挿入(STL/CLR)

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

*ヴァル*<br/>
挿入する要素の値。

*where*<br/>
前に挿入するコンテナー内の場所。

### <a name="remarks"></a>解説

各メンバー関数は、制御されたシーケンスの*位置*で指す要素の前に、残りのオペランドで指定されたシーケンスを挿入します。

最初のメンバー関数は、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 反復子によって指定された場所の前に単一の要素を挿入する場合に使用します。

2 番目のメンバー関数は、値*val*の*count*要素の繰り返しを挿入します。 この値を使用して、同じ値のすべてのコピーである 0 個以上の連続した要素を挿入します。

`InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合は、シーケンス`first`[ `last`, を挿入します。 別のシーケンスからコピーした連続した要素を 0 個以上挿入する場合に使用します。

4 番目のメンバー関数は、*右*で指定されたシーケンスを挿入します。 列挙子によって記述されたシーケンスを挿入する場合に使用します。

1 つの要素を挿入する場合、要素のコピー数は、挿入ポイントとシーケンスの終わりに近い要素の数に比例します。 (シーケンスの両端に 1 つ以上の要素を挿入する場合、要素のコピーは発生しません)。入力`InIt`反復子の場合、3 番目のメンバー関数は、シーケンス内の各要素に対して 1 つの挿入を効果的に実行します。 それ以外の場合、`N`要素を挿入する場合、要素のコピー数`N`は、挿入ポイントとシーケンスの近い末尾の間の要素数を足した線形になります。

### <a name="example"></a>例

```cpp
// cliext_vector_insert.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a single value using iterator
    cliext::vector<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// insert a repetition of values
    cliext::vector<wchar_t> c2;
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

## <a name="vectoriterator-stlclr"></a><a name="iterator"></a>ベクトル::反復器(STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスのランダム`T1`アクセス反復器として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
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

## <a name="vectoroperator-stlclr"></a><a name="op_as"></a>ベクトル::演算子=(STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
vector<Value>% operator=(vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバ オペレータは*オブジェクトに右*をコピーし、`*this`を返します。 これを使用して、制御されたシーケンスを*右側*の制御シーケンスのコピーに置き換えます。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_as.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="vectoroperatorstlclr"></a><a name="op"></a>ベクトル::演算子(STL/CLR)

指定した位置にある要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>パラメーター

*pos*<br/>
アクセスする要素の位置。

### <a name="remarks"></a>解説

メンバー演算子は *、pos*位置にある要素への参照を返します。位置がわかっている要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_sub.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using subscripting
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();

// change an entry and redisplay
    c1[1] = L'x';
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1[i]);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a x c
```

## <a name="vectorpop_back-stlclr"></a><a name="pop_back"></a>ベクトル::pソップバック(STL/CLR)

最後の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop_back();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最後の要素を削除します。 この値を使用して、後方の 1 つの要素でベクトルを短くします。

### <a name="example"></a>例

```cpp
// cliext_vector_pop_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorpush_back-stlclr"></a><a name="push_back"></a>ベクトル::push_back (STL/CLR)

新しい最後の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの末尾`val`に値を持つ要素を挿入します。 ベクターに別の要素を追加するために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_push_back.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorrbegin-stlclr"></a><a name="rbegin"></a>ベクトル::始まり(STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの最後の要素を指定する逆の反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_vector_rbegin.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items in reversed sequence
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="vectorreference-stlclr"></a><a name="reference"></a>ベクトル::リファレンス(STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_reference.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    cliext::vector<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

// modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::vector<wchar_t>::reference ref = *it;

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

## <a name="vectorrend-stlclr"></a><a name="rend"></a>ベクトル::レンド(STL /CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスの先頭を越えた位置を指す逆反復器を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_vector_rend.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first two items
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rend();
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

## <a name="vectorreserve-stlclr"></a><a name="reserve"></a>ベクトル::リザーブ(STL/CLR)

コンテナーの最小の拡張容量を確保します。

### <a name="syntax"></a>構文

```cpp
void reserve(size_type count);
```

#### <a name="parameters"></a>パラメーター

*count*<br/>
コンテナーの新しい最小容量。

### <a name="remarks"></a>解説

メンバー関数は、それ`capacity()`以降は少なくとも*カウント*を返すようになります。 これを使用して、指定したサイズにまで拡大するまで、コンテナーが制御シーケンスの記憶域を再割り当てする必要がないようにします。

### <a name="example"></a>例

```cpp
// cliext_vector_reserve.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for (int i = 0; i < c1.size(); ++i)
        System::Console::Write("{0} ", c1.at(i));
    System::Console::WriteLine();

// increase capacity
    cliext::vector<wchar_t>::size_type cap = c1.capacity();
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        cap, c1.size() <= cap);
    c1.reserve(cap + 5);
    System::Console::WriteLine("capacity() = {0}, ok = {1}",
        c1.capacity(), cap + 5 <= c1.capacity());
    return (0);
    }
```

```Output
a b c
capacity() = 4, ok = True
capacity() = 9, ok = True
```

## <a name="vectorresize-stlclr"></a><a name="resize"></a>ベクトル::サイズ変更(STL /CLR)

要素の数を変更します。

### <a name="syntax"></a>構文

```cpp
void resize(size_type new_size);
void resize(size_type new_size, value_type val);
```

#### <a name="parameters"></a>パラメーター

*new_size*<br/>
制御シーケンスの新しいサイズ。

*ヴァル*<br/>
埋め込み要素の値。

### <a name="remarks"></a>解説

メンバー関数は両方とも[vector::size (STL/CLR)](../dotnet/vector-size-stl-clr.md)`()`が*new_sizeを返*していることを確認します。 制御シーケンスを長くする必要がある場合、最初のメンバー関数は value`value_type()`を持つ要素を追加し、2 番目のメンバー関数は value *val*を持つ要素を追加します。 制御シーケンスを短くするために、両方のメンバー関数は、最後の要素[ベクトル::サイズ (STL/CLR)](../dotnet/vector-size-stl-clr.md)`() -``new_size`の時間を効果的に消去します。 この値を使用すると、現在の制御シーケンスをトリムまたはパディングすることにより、制御シーケンス*のサイズがnew_size*サイズが確保されます。

### <a name="example"></a>例

```cpp
// cliext_vector_resize.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container and pad with default values
    cliext::vector<wchar_t> c1;
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

## <a name="vectorreverse_iterator-stlclr"></a><a name="reverse_iterator"></a>ベクトル::reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、被制御シーケンスの反転反復`T3`器として使用できる、不特定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_vector_reverse_iterator.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" reversed
    cliext::vector<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="vectorsize-stlclr"></a><a name="size"></a>ベクトル::サイズ(STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 この値を使用して、現在の制御シーケンス内の要素の数を決定します。 シーケンスのサイズが 0 以外であるかどうかが重要な場合は[、「vector::empty (STL/CLR)」](../dotnet/vector-empty-stl-clr.md)`()`を参照してください。

### <a name="example"></a>例

```cpp
// cliext_vector_size.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorsize_type-stlclr"></a><a name="size_type"></a>ベクトル::size_type (STL/CLR)

2 つの要素間の距離を表す、符号付きの型です。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_vector_size_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    cliext::vector<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="vectorswap-stlclr"></a><a name="swap"></a>ベクトル::スワップ(STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

メンバー関数は、 と*の*間`*this`で制御されたシーケンスを入れ替えます。 これは一定の時間で行われ、例外はスローされません。 2 つのコンテナーの内容を交換する簡単な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_swap.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct another container with repetition of values
    cliext::vector<wchar_t> c2(5, L'x');
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

## <a name="vectorto_array-stlclr"></a><a name="to_array"></a>ベクトル::to_array (STL/CLR)

制御されたシーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

メンバー関数は、制御されたシーケンスを含む配列を返します。 配列形式で制御シーケンスのコピーを取得するために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_to_array.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
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

## <a name="vectorvalue_type-stlclr"></a><a name="value_type"></a>ベクトル::value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメータ Value のシノニム*です*。

### <a name="example"></a>例

```cpp
// cliext_vector_value_type.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c" using value_type
    for (cliext::vector<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::vector<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="vectorvector-stlclr"></a><a name="vector"></a>ベクトル::ベクトル(STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
vector();
vector(vector<Value>% right);
vector(vector<Value>^ right);
explicit vector(size_type count);
vector(size_type count, value_type val);
template<typename InIt>
    vector(InIt first, InIt last);
vector(System::Collections::Generic::IEnumerable<Value>^ right);
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

*ヴァル*<br/>
挿入する要素の値。

### <a name="remarks"></a>解説

コンストラクター:

`vector();`

は、要素なしで制御されたシーケンスを初期化します。 空の初期制御シーケンスを指定するために使用します。

コンストラクター:

`vector(vector<Value>% right);`

は、シーケンス [`right.begin()`, `right.end()`) で制御シーケンスを初期化します。 これを使用して、ベクトル オブジェクト*の右*で制御されるシーケンスのコピーである初期被制御シーケンスを指定します。

コンストラクター:

`vector(vector<Value>^ right);`

は、シーケンス [`right->begin()`, `right->end()`) で制御シーケンスを初期化します。 このクラスを使用して、ハンドルが*right*であるベクトル オブジェクトによって制御されるシーケンスのコピーである初期被制御シーケンスを指定します。

コンストラクター:

`explicit vector(size_type count);`

は、各 count*要素を*持つ制御`value_type()`されたシーケンスを value で初期化します。 この値を使用して、既定値を持つ要素をすべてコンテナーに格納します。

コンストラクター:

`vector(size_type count, value_type val);`

は、値*val*を持つ*カウント*要素を使用して、制御されたシーケンスを初期化します。 この値を使用して、同じ値を持つ要素をすべてコンテナーに埋めます。

コンストラクター:

`template<typename InIt>`

`vector(InIt first, InIt last);`

は、シーケンス [`first`, `last`) で制御シーケンスを初期化します。 これを使用して、制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`vector(System::Collections::Generic::IEnumerable<Value>^ right);`

は、列挙子*right*で指定されたシーケンスで制御シーケンスを初期化します。 これを使用して、制御されたシーケンスを列挙子によって記述された別のシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_vector_construct.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
// construct an empty container
    cliext::vector<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct with a repetition of default values
    cliext::vector<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

// construct with a repetition of values
    cliext::vector<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an iterator range
    cliext::vector<wchar_t>::iterator it = c3.end();
    cliext::vector<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct with an enumeration
    cliext::vector<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    cliext::vector<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying a container handle
    cliext::vector<wchar_t> c8(%c3);
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

## <a name="operator-vector-stlclr"></a><a name="op_neq"></a>演算子!= (ベクター) (STL/CLR)

ベクトルが比較に等しくない。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator!=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(left == right)`を返します。 2 つのベクトルが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_ne.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lt"></a>演算子&lt;(ベクター) (STL/CLR)

比較より少ないベクトル。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、その値も true である`i`最下位の`!(right[i] < left[i])`位置に対して`left[i] < right[i]`true を返します。 それ以外の場合`left->size() < right->size()`は、2 つのベクトルが要素によって比較されるときに *、左*が*右*より前に並べられるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_lt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorlt-vector-stlclr"></a><a name="op_lteq"></a>演算子&lt;= (ベクター) (STL/CLR)

ベクトルの比較が小さいか等しい。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(right < left)`を返します。 2 つのベクトルが要素ごとに比較されるときに *、左*が*右*の後に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_le.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operator-vector-stlclr"></a><a name="op_eq"></a>演算子==(ベクトル) (STL/CLR)

ベクトル等比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator==(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、*左右*で制御されるシーケンスの長さが同*right*じ場合にのみ true を返し、`i`各`left[i] ==``right[i]`位置に対して true を返します。 2 つのベクトルが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_eq.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gt"></a>演算子&gt;(ベクター) (STL/CLR)

比較より大きいベクトル。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`right``<``left`を返します。 2 つのベクトルが要素ごとに比較されるときに *、左*が*右*の後に並べ替えられたかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_gt.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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

## <a name="operatorgt-vector-stlclr"></a><a name="op_gteq"></a>演算子&gt;= (ベクター) (STL/CLR)

ベクトルの比較が大きいか等しいか。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>=(vector<Value>% left,
        vector<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、`!(left < right)`を返します。 2 つのベクトルが要素ごとに比較されるときに *、左*が*右*より前に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_vector_operator_ge.cpp
// compile with: /clr
#include <cliext/vector>

int main()
    {
    cliext::vector<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    cliext::vector<wchar_t> c2;
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
