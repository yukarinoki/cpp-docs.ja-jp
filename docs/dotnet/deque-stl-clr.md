---
title: deque (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::deque
- cliext::deque::assign
- cliext::deque::at
- cliext::deque::back
- cliext::deque::back_item
- cliext::deque::begin
- cliext::deque::clear
- cliext::deque::const_iterator
- cliext::deque::const_reference
- cliext::deque::const_reverse_iterator
- cliext::deque::deque
- cliext::deque::difference_type
- cliext::deque::empty
- cliext::deque::end
- cliext::deque::erase
- cliext::deque::front
- cliext::deque::front_item
- cliext::deque::generic_container
- cliext::deque::generic_iterator
- cliext::deque::generic_reverse_iterator
- cliext::deque::generic_value
- cliext::deque::insert
- cliext::deque::iterator
- cliext::deque::operator!=
- cliext::deque::operator[]
- cliext::deque::pop_back
- cliext::deque::pop_front
- cliext::deque::push_back
- cliext::deque::push_front
- cliext::deque::rbegin
- cliext::deque::reference
- cliext::deque::rend
- cliext::deque::resize
- cliext::deque::reverse_iterator
- cliext::deque::size
- cliext::deque::size_type
- cliext::deque::swap
- cliext::deque::to_array
- cliext::deque::value_type
- cliext::deque::operator<
- cliext::deque::operator<=
- cliext::deque::operator=
- cliext::deque::operator==
- cliext::deque::operator>
- cliext::deque::operator>=
helpviewer_keywords:
- deque class [STL/CLR]
- <deque> header [STL/CLR]
- <cliext/deque> header [STL/CLR]
- assign member [STL/CLR]
- assign member [STL/CLR]
- at member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- begin member [STL/CLR]
- clear member [STL/CLR]
- const_iterator member [STL/CLR]
- const_reference member [STL/CLR]
- const_reverse_iterator member [STL/CLR]
- deque member [STL/CLR]
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
- operator!= member [STL/CLR]
- operator member [] [STL/CLR]
- pop_back member [STL/CLR]
- pop_front member [STL/CLR]
- push_back member [STL/CLR]
- push_front member [STL/CLR]
- rbegin member [STL/CLR]
- reference member [STL/CLR]
- rend member [STL/CLR]
- resize member [STL/CLR]
- reverse_iterator member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
ms.assetid: dd669da3-3c0e-45e9-8596-f6b483720941
ms.openlocfilehash: 75c83240b9125628fd5121368af547a5266bfb5c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221498"
---
# <a name="deque-stlclr"></a>deque (STL/CLR)

このテンプレートクラスは、ランダムアクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナーを使用し `deque` て、連続したストレージのブロックのように見える要素のシーケンスを管理しますが、その他の要素をコピーしなくても、いずれかの端で拡張または縮小することができます。 したがって、を効率的に実装でき `double-ended queue` ます。 (したがって、という名前になります)。

次の説明で、 `GValue` は、後者が参照型である場合を除き、と同じです `Value` 。この場合、は `Value^` です。

## <a name="syntax"></a>構文

```cpp
template<typename Value>
    ref class deque
        :   public
        System::ICloneable,
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<GValue>,
        System::Collections::Generic::ICollection<GValue>,
        System::Collections::Generic::IList<GValue>,
        Microsoft::VisualC::StlClr::IDeque<GValue>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*GValue*<br/>
被制御シーケンス内の要素のジェネリック型。

*Value*<br/>
被制御シーケンス内の要素の型。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/deque>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型の定義|説明|
|---------------------|-----------------|
|[deque::const_iterator (STL/CLR)](#const_iterator)|被制御シーケンスの定数反復子の型です。|
|[deque::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[deque::const_reverse_iterator (STL/CLR)](#const_reverse_iterator)|被制御シーケンスの定数反転反復子の型です。|
|[deque::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[deque::generic_container (STL/CLR)](#generic_container)|コンテナーのジェネリックインターフェイスの型。|
|[deque::generic_iterator (STL/CLR)](#generic_iterator)|コンテナーのジェネリックインターフェイスの反復子の型。|
|[deque::generic_reverse_iterator (STL/CLR)](#generic_reverse_iterator)|コンテナーのジェネリックインターフェイスの反転反復子の型。|
|[deque::generic_value (STL/CLR)](#generic_value)|コンテナーのジェネリックインターフェイスの要素の型。|
|[deque::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[deque::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[deque::reverse_iterator (STL/CLR)](#reverse_iterator)|被制御シーケンスの反転反復子の型です。|
|[deque::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[deque::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[deque::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[deque::at (STL/CLR)](#at)|指定した位置にある要素にアクセスします。|
|[deque::back (STL/CLR)](#back)|最後の要素にアクセスします。|
|[deque::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[deque::clear (STL/CLR)](#clear)|すべての要素を削除します。|
|[deque::deque (STL/CLR)](#deque)|コンテナー オブジェクトを構築します。|
|[deque::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[deque::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[deque::erase (STL/CLR)](#erase)|指定した位置にある要素を削除します。|
|[deque::front (STL/CLR)](#front)|最初の要素にアクセスします。|
|[deque::insert (STL/CLR)](#insert)|指定した位置に要素を追加します。|
|[deque::pop_back (STL/CLR)](#pop_back)|最後の要素を削除します。|
|[deque::pop_front (STL/CLR)](#pop_front)|最初の要素を削除します。|
|[deque::push_back (STL/CLR)](#push_back)|新しい最後の要素を追加します。|
|[deque::push_front (STL/CLR)](#push_front)|新しい最初の要素を追加します。|
|[deque::rbegin (STL/CLR)](#rbegin)|反転被制御シーケンスの先頭を指定します。|
|[deque::rend (STL/CLR)](#rend)|反転被制御シーケンスの末尾を指定します。|
|[deque::resize (STL/CLR)](#resize)|要素の数を変更します。|
|[deque::size (STL/CLR)](#size)|要素の数をカウントします。|
|[deque::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|
|[deque::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|

|プロパティ|Description|
|--------------|-----------------|
|[deque::back_item (STL/CLR)](#back_item)|最後の要素にアクセスします。|
|[deque::front_item (STL/CLR)](#front_item)|最初の要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[deque::operator!= (STL/CLR)](#op_neq)|2つ `deque` のオブジェクトが等しくないかどうかを判断します。|
|[deque::operator(STL/CLR)](#operator)|指定した位置にある要素にアクセスします。|
|[operator< (deque) (STL/CLR)](#op_lt)|`deque`オブジェクトが別のオブジェクトより小さいかどうかを判断し `deque` ます。|
|[operator<= (deque) (STL/CLR)](#op_lteq)|オブジェクトが別のオブジェクト以下かどうかを判断し `deque` `deque` ます。|
|[operator = (deque) (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[operator== (deque) (STL/CLR)](#op_eq)|オブジェクトが別のオブジェクトと等しいかどうかを判断し `deque` `deque` ます。|
|[operator> (deque) (STL/CLR)](#op_gt)|`deque`オブジェクトが他のオブジェクトより大きいかどうかを判断し `deque` ます。|
|[operator>= (deque) (STL/CLR)](#op_gteq)|オブジェクトが別のオブジェクト以上かどうかを判断し `deque` `deque` ます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|<xref:System.Collections.IEnumerable>|要素を順番に処理します。|
|<xref:System.Collections.ICollection>|要素のグループを維持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|型指定された要素を順番に処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|
|<xref:System.Collections.Generic.IList%601>|型指定された要素の順序付けされたグループを維持します。|
|IDeque<値\>|ジェネリックコンテナーを管理します。|

## <a name="remarks"></a>解説

オブジェクトは、要素のブロックを指定するハンドルの格納された配列を通じて、制御するシーケンスのストレージを割り当てて解放し `Value` ます。 配列は必要に応じて拡張されます。 増加は、新しい要素の前または後にかかるコストが一定時間で、残りの要素が影響を受けないようにするために発生します。 また、いずれかの端にある要素を一定の時間で削除し、残りの要素を中断せずに削除することもできます。 このため、deque は、テンプレートクラス[キュー (stl/clr)](../dotnet/queue-stl-clr.md)またはテンプレートクラス[スタック (stl/clr)](../dotnet/stack-stl-clr.md)の基になるコンテナーに適しています。

`deque`オブジェクトはランダムアクセス反復子をサポートします。つまり、要素を、最初の (front) 要素の場合は0から、last (back) 要素の場合は[deque:: SIZE (STL/CLR)](#size)に数えて、数値位置を指定して直接参照できます `() - 1` 。 また、deque がテンプレートクラス[priority_queue (STL/CLR)](../dotnet/priority-queue-stl-clr.md)の基になるコンテナーの候補として適していることも意味します。

Deque iterator は、関連付けられている deque オブジェクトへのハンドルを、指定する要素のバイアスと共に格納します。 反復子は、関連付けられているコンテナーオブジェクトと共にのみ使用できます。 Deque 要素のバイアスは、必ずしもその位置と同じである必要は*ありません*。 挿入された最初の要素はバイアスゼロを持ち、次に追加される要素はバイアス1を持ちますが、次の先頭の要素にはバイアス-1 があります。

いずれかの端に要素を挿入または消去しても、有効なバイアスで格納されている要素の値は変更*されません*。 ただし、内部要素を挿入または消去*する*と、指定したバイアスで格納されている要素の値を変更できるため、反復子によって指定された値も変更される可能性があります。 (コンテナーは、挿入の前に穴を作成したり、消去後に穴を埋めるために、要素を上下にコピーすることが必要になる場合があります)。ただし、そのバイアスによって有効な要素が指定されていれば、deque iterator は有効なままです。 さらに、有効な反復子は dereferencable のままです。これを使用すると、指定した要素の値にアクセスしたり変更したりすることができます。これは、バイアスがによって返される反復子のバイアスと等しくない場合に限り `end()` ます。

要素を消去または削除すると、格納されている値のデストラクターが呼び出されます。 コンテナーを破棄すると、すべての要素が消去されます。 したがって、要素の型が ref クラスであるコンテナーは、コンテナーの直後要素が存在しないことを保証します。 ただし、ハンドルのコンテナーが要素を破棄し*ない*ことに注意してください。

## <a name="members"></a>メンバー

## <a name="dequeassign-stlclr"></a><a name="assign"></a>deque:: assign (STL/CLR)

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

最初のメンバー関数は、被制御シーケンスを、値*val*の*count*要素の繰り返しで置き換えます。 このメソッドを使用して、すべての要素が同じ値を持つコンテナーを塗りつぶします。

`InIt`が整数型の場合、2番目のメンバー関数はと同じように動作し `assign((size_type)first, (value_type)last)` ます。 それ以外の場合は、被制御シーケンスをシーケンス [ `first` ,) で置き換え `last` ます。 このメソッドを使用して、被制御シーケンスを別のシーケンスにコピーします。

3番目のメンバー関数は、被制御シーケンスを列挙子*権限*によって指定されたシーケンスに置き換えます。 このメソッドを使用して、被制御シーケンスを列挙子によって記述されたシーケンスのコピーにします。

### <a name="example"></a>例

```cpp
// cliext_deque_assign.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // assign a repetition of values
    cliext::deque<wchar_t> c2;
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

## <a name="dequeat-stlclr"></a><a name="at"></a>deque:: at (STL/CLR)

指定した位置にある要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference at(size_type pos);
```

#### <a name="parameters"></a>パラメーター

*po*<br/>
アクセスする要素の位置。

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの要素への参照を位置*pos*に返します。このメソッドを使用して、既知の位置を持つ要素の読み取りまたは書き込みを行います。

### <a name="example"></a>例

```cpp
// cliext_deque_at.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeback-stlclr"></a><a name="back"></a>deque:: back (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference back();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最後の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_deque_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeback_item-stlclr"></a><a name="back_item"></a>deque:: back_item (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type back_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最後の要素にアクセスします。この要素は、空にすることはできません。 このメソッドは、最後の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_deque_back_item.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequebegin-stlclr"></a><a name="begin"></a>deque:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定するランダムアクセス反復子を返します。 これを使用して被制御シーケンスの現在の先頭 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_deque_begin.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::deque<wchar_t>::iterator it = c1.begin();
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

## <a name="dequeclear-stlclr"></a><a name="clear"></a>deque:: clear (STL/CLR)

すべての要素を削除します。

### <a name="syntax"></a>構文

```cpp
void clear();
```

### <a name="remarks"></a>解説

このメンバー関数は、実質的に[deque:: erase (stl](#erase) /clr) `(` [deque:: begin (](#begin) stl/clr) `(),` [deque:: end (stl/clr)](#end) `())` を呼び出します。 このメソッドを使用して、被制御シーケンスが空であることを確認します。

### <a name="example"></a>例

```cpp
// cliext_deque_clear.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeconst_iterator-stlclr"></a><a name="const_iterator"></a>deque:: const_iterator (STL/CLR)

被制御シーケンスの定数反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T2 const_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T2` 被制御シーケンスの定数ランダムアクセス反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_const_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        System::Console::Write("{0} ", *cit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="dequeconst_reference-stlclr"></a><a name="const_reference"></a>deque:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_const_reference.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::deque<wchar_t>::const_iterator cit = c1.begin();
    for (; cit != c1.end(); ++cit)
        {   // get a const reference to an element
        cliext::deque<wchar_t>::const_reference cref = *cit;
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="dequeconst_reverse_iterator-stlclr"></a><a name="const_reverse_iterator"></a>deque:: const_reverse_iterator (STL/CLR)

被制御シーケンスの定数反転反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef T4 const_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T4` 被制御シーケンスの定数反転反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_const_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::deque<wchar_t>::const_reverse_iterator crit = c1.rbegin();
    cliext::deque<wchar_t>::const_reverse_iterator crend = c1.rend();
    for (; crit != crend; ++crit)
        System::Console::Write("{0} ", *crit);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="dequedeque-stlclr"></a><a name="deque"></a>deque::d の場合 (STL/CLR)

コンテナー オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
deque();
deque(deque<Value>% right);
deque(deque<Value>^ right);
explicit deque(size_type count);
deque(size_type count, value_type val);
template<typename InIt>
    deque(InIt first, InIt last);
deque(System::Collections::Generic::IEnumerable<Value>^ right);
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

`deque();`

要素を含まない被制御シーケンスを初期化します。 このメソッドを使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`deque(deque<Value>% right);`

シーケンス [,) を使用して被制御シーケンスを初期化し `right.begin()` `right.end()` ます。 このメソッドを使用して、deque オブジェクト*権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。 反復子の詳細については、「 [deque:: begin (stl/clr)](#begin) 」および「 [deque:: end (stl/clr)](#end)」を参照してください。

コンストラクター:

`deque(deque<Value>^ right);`

シーケンス [,) を使用して被制御シーケンスを初期化し `right->begin()` `right->end()` ます。 このメソッドを使用して、ハンドルが*right*である deque オブジェクトによって制御されるシーケンスのコピーである、最初の被制御シーケンスを指定します。

コンストラクター:

`explicit deque(size_type count);`

値を持つ*カウント*要素を使用して被制御シーケンスを初期化し `value_type()` ます。 このメソッドを使用して、すべての要素に既定値が設定されたコンテナーにデータを格納します。

コンストラクター:

`deque(size_type count, value_type val);`

値*val*を持つ*カウント*要素を使用して被制御シーケンスを初期化します。 このメソッドを使用して、すべての要素が同じ値を持つコンテナーを塗りつぶします。

コンストラクター:

`template<typename InIt>`

`deque(InIt first, InIt last);`

シーケンス [,) を使用して被制御シーケンスを初期化し `first` `last` ます。 このメソッドを使用して、被制御シーケンスを別のシーケンスのコピーにします。

コンストラクター:

`deque(System::Collections::Generic::IEnumerable<Value>^ right);`

列挙子*権限*によって指定されたシーケンスを使用して、被制御シーケンスを初期化します。 このメソッドを使用して、被制御シーケンスを、列挙子によって記述された別のシーケンスのコピーとして作成します。

### <a name="example"></a>例

```cpp
// cliext_deque_construct.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
// construct an empty container
    cliext::deque<wchar_t> c1;
    System::Console::WriteLine("size() = {0}", c1.size());

    // construct with a repetition of default values
    cliext::deque<wchar_t> c2(3);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", (int)elem);
    System::Console::WriteLine();

    // construct with a repetition of values
    cliext::deque<wchar_t> c3(6, L'x');
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    cliext::deque<wchar_t>::iterator it = c3.end();
    cliext::deque<wchar_t> c4(c3.begin(), --it);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an enumeration
    cliext::deque<wchar_t> c5(   // NOTE: cast is not needed
        (System::Collections::Generic::IEnumerable<wchar_t>^)%c3);
    for each (wchar_t elem in c5)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    cliext::deque<wchar_t> c7(c3);
    for each (wchar_t elem in c7)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    cliext::deque<wchar_t> c8(%c3);
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

## <a name="dequedifference_type-stlclr"></a><a name="difference_type"></a>deque::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、署名された要素の数を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_difference_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::deque<wchar_t>::difference_type diff = 0;
    for (cliext::deque<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it) ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);

    // compute negative difference
    diff = 0;
    for (cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequeempty-stlclr"></a><a name="empty"></a>deque:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは、 [deque:: size (STL/CLR)](#size)に相当 `() == 0` します。 このメソッドを使用して、deque が空かどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_empty.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequeend-stlclr"></a><a name="end"></a>deque:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示すランダムアクセス反復子を返します。 これを使用して被制御シーケンスの現在の (`current`) 末尾を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_deque_end.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last two items
    cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequeerase-stlclr"></a><a name="erase"></a>deque:: erase (STL/CLR)

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

最初のメンバー関数は、によって示さ*れる*被制御シーケンスの要素を削除します。 このメソッドを使用して、1つの要素を削除します。

2 番目のメンバー関数は、範囲 [`first`, `last`) の被制御シーケンスの要素を削除します。 これを使用して、0個以上の連続する要素を削除します。

両方のメンバー関数は、削除された要素の後に残った最初の要素を指定する反復子を返します。そのような要素が存在しない場合は、 [deque:: end (STL/CLR)](#end)を返し `()` ます。

要素が消去されるときに、要素のコピー数は、消去の終了位置とシーケンスの一番近い方の要素の数で線形になります。 (シーケンスの両端で1つ以上の要素を消去すると、要素のコピーは行われません)。

### <a name="example"></a>例

```cpp
// cliext_deque_erase.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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
    cliext::deque<wchar_t>::iterator it = c1.end();
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

## <a name="dequefront-stlclr"></a><a name="front"></a>deque:: front (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference front();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素への参照を返します。この要素は、空にすることはできません。 これは、最初の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_deque_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequefront_item-stlclr"></a><a name="front_item"></a>deque:: front_item (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type front_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最初の要素にアクセスします。この要素は、空にすることはできません。 これは、最初の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_deque_front_item.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequegeneric_container-stlclr"></a><a name="generic_container"></a>deque:: generic_container (STL/CLR)

コンテナーのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::
    IDeque<generic_value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_generic_container.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
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

## <a name="dequegeneric_iterator-stlclr"></a><a name="generic_iterator"></a>deque:: generic_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ContainerRandomAccessIterator<generic_value> generic_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_generic_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequegeneric_reverse_iterator-stlclr"></a><a name="generic_reverse_iterator"></a>deque:: generic_reverse_iterator (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する逆順反復子の型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::Generic::
    ReverseRandomAccessIterator<generic_value> generic_reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用できる汎用反転反復子を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_generic_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_reverse_iterator gcit = gc1->rbegin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequegeneric_value-stlclr"></a><a name="generic_value"></a>deque:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、 `GValue` このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_generic_value.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    cliext::deque<wchar_t>::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    cliext::deque<wchar_t>::generic_iterator gcit = gc1->begin();
    cliext::deque<wchar_t>::generic_value gcval = *gcit;
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

## <a name="dequeinsert-stlclr"></a><a name="insert"></a>deque:: insert (STL/CLR)

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

各メンバー関数は、被制御シーケンス内の*where*が指す要素の前に、残りのオペランドによって指定されたシーケンスを挿入します。

1つ目のメンバー関数は、値*val*を持つ要素を挿入し、新しく挿入された要素を指定する反復子を返します。 反復子によって指定された場所の前に1つの要素を挿入する場合に使用します。

2番目のメンバー関数は、値*val*の*count*要素の繰り返しを挿入します。 これを使用して、同じ値のすべてのコピーである0個以上の連続する要素を挿入します。

`InIt` が整数型である場合、3 番目のメンバー関数は `insert(where, (size_type)first, (value_type)last)` と同じように動作します。 それ以外の場合は、シーケンス [ `first` ,) を挿入 `last` します。 このメソッドを使用して、別のシーケンスからコピーされた0個以上の連続する要素を挿入します。

4番目のメンバー関数は、*右側*に指定されたシーケンスを挿入します。 このメソッドを使用して、列挙子によって記述されたシーケンスを挿入します。

1つの要素を挿入する場合、要素のコピー数は、挿入ポイントとそれに近いシーケンスの末尾との間の要素の数で線形になります。 (シーケンスの両端に1つ以上の要素を挿入する場合、要素のコピーは行われません)。`InIt`が入力反復子の場合、3番目のメンバー関数は、シーケンス内の各要素に対して1つの挿入を効果的に実行します。 それ以外の場合、要素を挿入するときに、 `N` 要素のコピーの数には、 `N` 挿入ポイントとそれに近いシーケンスの末尾との間の要素数が加算されます。

### <a name="example"></a>例

```cpp
// cliext_deque_insert.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a single value using iterator
    cliext::deque<wchar_t>::iterator it = c1.begin();
    System::Console::WriteLine("insert(begin()+1, L'x') = {0}",
        *c1.insert(++it, L'x'));
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // insert a repetition of values
    cliext::deque<wchar_t> c2;
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

## <a name="dequeiterator-stlclr"></a><a name="iterator"></a>deque:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、 `T1` 被制御シーケンスのランダムアクセス反復子として使用できる、未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    cliext::deque<wchar_t>::iterator it = c1.begin();
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

## <a name="dequeoperator-stlclr"></a><a name="op_neq"></a>deque:: operator! = (STL/CLR)

Deque が等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator!=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left == right)` ます。 このメソッドを使用して、2つの要素が要素によって比較されるときに、 *left*が*right*と同じ順序で並んでいないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_ne.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="dequeoperatorstlclr"></a><a name="operator"></a>deque:: operator (STL/CLR)

指定した位置にある要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference operator[](size_type pos);
```

#### <a name="parameters"></a>パラメーター

*po*<br/>
アクセスする要素の位置。

### <a name="remarks"></a>解説

このメンバー演算子は、 *pos*の位置にある要素に referene を返します。このメソッドを使用して、既知の位置にある要素にアクセスします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_sub.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepop_back-stlclr"></a><a name="pop_back"></a>deque::p op_back (STL/CLR)

最後の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop_back();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素を削除します。この要素は空にすることはできません。 これを使用して、deque を1つ後ろの要素で短くします。

### <a name="example"></a>例

```cpp
// cliext_deque_pop_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepop_front-stlclr"></a><a name="pop_front"></a>deque::p op_front (STL/CLR)

最初の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop_front();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素を削除します。この要素は空でない必要があります。 このメソッドを使用して、前に1つの要素で deque を短縮します。

### <a name="example"></a>例

```cpp
// cliext_deque_pop_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepush_back-stlclr"></a><a name="push_back"></a>deque::p ush_back (STL/CLR)

新しい最後の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push_back(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、 `val` 被制御シーケンスの末尾に値を持つ要素を挿入します。 このメソッドを使用して、deque に別の要素を追加します。

### <a name="example"></a>例

```cpp
// cliext_deque_push_back.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequepush_front-stlclr"></a><a name="push_front"></a>deque::p ush_front (STL/CLR)

新しい最初の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push_front(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、 `val` 被制御シーケンスの先頭に値を持つ要素を挿入します。 このメソッドを使用して、deque に別の要素の前に付加します。

### <a name="example"></a>例

```cpp
// cliext_deque_push_front.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequerbegin-stlclr"></a><a name="rbegin"></a>deque:: rbegin (STL/CLR)

反転被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rbegin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素、または空のシーケンスの先頭の次の位置を指定する反転反復子を返します。 したがって、これは反転シーケンスの `beginning` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の (`current`) 先頭を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_deque_rbegin.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items in reversed sequence
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="dequereference-stlclr"></a><a name="reference"></a>deque:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_reference.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    cliext::deque<wchar_t>::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::deque<wchar_t>::reference ref = *it;
        System::Console::Write("{0} ", ref);
        }
    System::Console::WriteLine();

    // modify contents " a b c"
    for (it = c1.begin(); it != c1.end(); ++it)
        {   // get a reference to an element
        cliext::deque<wchar_t>::reference ref = *it;

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

## <a name="dequerend-stlclr"></a><a name="rend"></a>deque:: rend (STL/CLR)

反転被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
reverse_iterator rend();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの先頭を越えた位置を示す反転反復子を返します。 したがって、これは反転シーケンスの `end` を指定します。 これを使用して被制御シーケンスの逆順に見た現在の末尾 (`current`) を指定する反復子を取得しますが、このステータスは被制御シーケンスの長さが変わると変化することがあります。

### <a name="example"></a>例

```cpp
// cliext_deque_rend.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rend();
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

## <a name="dequeresize-stlclr"></a><a name="resize"></a>deque:: resize (STL/CLR)

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

メンバー関数はどちらも、 [deque:: size (STL/CLR)](#size) `()` その後が*new_size*を返すことを保証します。 被制御シーケンスを長くする必要がある場合、最初のメンバー関数は値を持つ要素を追加し、 `value_type()` 2 番目のメンバー関数は値*val*を持つ要素を追加します。 被制御シーケンスを短くするために、両方のメンバー関数は、最後の要素[deque:: size (STL/CLR)](#size)の時刻を効果的に消去し `() -` `new_size` ます。 このメソッドを使用すると、現在の被制御シーケンスのトリミングまたは埋め込みによって、被制御シーケンスのサイズが*new_size*になるようにすることができます。

### <a name="example"></a>例

```cpp
// cliext_deque_resize.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
// construct an empty container and pad with default values
    cliext::deque<wchar_t> c1;
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

## <a name="dequereverse_iterator-stlclr"></a><a name="reverse_iterator"></a>deque:: reverse_iterator (STL/CLR)

被制御シーケンスの反転反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T3 reverse_iterator;
```

### <a name="remarks"></a>解説

この型は、 `T3` 被制御シーケンスの反転反復子として使用できる指定されていない型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_deque_reverse_iterator.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" reversed
    cliext::deque<wchar_t>::reverse_iterator rit = c1.rbegin();
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

## <a name="dequesize-stlclr"></a><a name="size"></a>deque:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスのサイズがゼロ以外であるかどうかは、「 [deque:: empty (STL/CLR)](#empty)」を参照してください `()` 。

### <a name="example"></a>例

```cpp
// cliext_deque_size.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequesize_type-stlclr"></a><a name="size_type"></a>deque:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_deque_size_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    cliext::deque<wchar_t>::size_type diff = c1.end() - c1.begin();
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
    }
```

```Output
a b c
end()-begin() = 3
```

## <a name="dequeswap-stlclr"></a><a name="swap"></a>deque:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、との間で被制御シーケンスを交換し **`*this`** ます。 *right* この処理は一定時間に実行され、例外はスローされません。 2つのコンテナーの内容を簡単に交換する方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_deque_swap.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::deque<wchar_t> c2(5, L'x');
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

## <a name="dequeto_array-stlclr"></a><a name="to_array"></a>deque:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_deque_to_array.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
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

## <a name="dequevalue_type-stlclr"></a><a name="value_type"></a>deque:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター*値*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_deque_value_type.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c" using value_type
    for (cliext::deque<wchar_t>::iterator it = c1.begin();
        it != c1.end(); ++it)
        {   // store element in value_type object
        cliext::deque<wchar_t>::value_type val = *it;

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operatorlt-deque-stlclr"></a><a name="op_lt"></a>operator &lt; (deque) (STL/CLR)

Deque 未満の比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、が true である場合にも true を返し `i` `!(right[i] < left[i])` `left[i] < right[i]` ます。 それ以外の場合は、このメソッドを `left->size() < right->size()` 使用して、2つの要素が要素によって比較されたときに、 *left*が*right*の前に配置されているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_lt.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorlt-deque-stlclr"></a><a name="op_lteq"></a>operator &lt; = (deque) (STL/CLR)

Deque 以下の比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator<=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(right < left)` ます。 このメソッドを使用して、2つの要素が要素別に比較されるときに、 *right*の後に*left*が順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_le.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operator-deque-stlclr"></a><a name="op_as"></a>operator = (deque) (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
deque<Value>% operator=(deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナー。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに*right*をコピーし、を返し **`*this`** ます。 このメソッドを使用して、被制御シーケンスを*右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_as.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operator-deque-stlclr"></a><a name="op_eq"></a>operator = = (deque) (STL/CLR)

Deque 等値比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator==(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、*左*と*右*で制御されるシーケンスの長さが同じで、各位置についてがである場合にのみ true を返し `i` `left[i] ==` `right[i]` ます。 このメソッドを使用して、2つの要素が要素によって比較されるときに、 *left*が*right*と同じ順序で並んでいるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_eq.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorgt-deque-stlclr"></a><a name="op_gt"></a>operator &gt; (deque) (STL/CLR)

Deque は比較よりも大きくなります。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `right` `<` `left` ます。 このメソッドを使用して、2つの要素が要素によって比較されたときに、 *left*が*right*の後に配置されているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_gt.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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

## <a name="operatorgt-deque-stlclr"></a><a name="op_gteq"></a>operator &gt; = (deque) (STL/CLR)

Deque 以上の比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value>
    bool operator>=(deque<Value>% left,
        deque<Value>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left` `<` `right)` ます。 このメソッドを使用して、2つの要素が要素別に比較されるときに、 *left*が*right*の前に順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_deque_operator_ge.cpp
// compile with: /clr
#include <cliext/deque>

int main()
    {
    cliext::deque<wchar_t> c1;
    c1.push_back(L'a');
    c1.push_back(L'b');
    c1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    cliext::deque<wchar_t> c2;
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
