---
description: '詳細情報: adapter (STL/CLR)'
title: adapter (STL/CLR)
ms.date: 06/15/2018
ms.topic: reference
f1_keywords:
- <cliext/adapter>
- cliext::collection_adapter
- cliext::collection_adapter::base
- cliext::collection_adapter::begin
- cliext::collection_adapter::collection_adapter
- cliext::collection_adapter::difference_type
- cliext::collection_adapter::end
- cliext::collection_adapter::iterator
- cliext::collection_adapter::key_type
- cliext::collection_adapter::mapped_type
- cliext::collection_adapter::operator=
- cliext::collection_adapter::reference
- cliext::collection_adapter::size
- cliext::collection_adapter::size_type
- cliext::collection_adapter::swap
- cliext::collection_adapter::value_type
- cliext::make_collection
- cliext::range_adapter
- cliext::operator=
- cliext::range_adapter::operator=
- cliext::range_adapter::range_adapter
helpviewer_keywords:
- <adapter> header [STL/CLR]
- adapter [STL/CLR]
- <cliext/adapter> header [STL/CLR]
- collection_adapter class [STL/CLR]
- base member [STL/CLR]
- begin member [STL/CLR]
- collection_adapter member [STL/CLR]
- difference_type member [STL/CLR]
- end member [STL/CLR]
- iterator member [STL/CLR]
- key_type member [STL/CLR]
- mapped_type member [STL/CLR]
- operator= member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- swap member [STL/CLR]
- value_type member [STL/CLR]
- make_collection function [STL/CLR]
- range_adapter class [STL/CLR]
- operator= member [STL/CLR]
- range_adapter member [STL/CLR]
ms.assetid: 71ce7e51-42b6-4f70-9595-303791a97677
ms.openlocfilehash: 66e6346c644bc0d176d90701722cfcd90cbb3590
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97116420"
---
# <a name="adapter-stlclr"></a>adapter (STL/CLR)

STL/CLR ヘッダーは、 `<cliext/adapter>` 2 つのテンプレートクラス ( `collection_adapter` と `range_adapter` ) と、テンプレート関数を指定し `make_collection` ます。

## <a name="syntax"></a>構文

```cpp
#include <cliext/adapter>
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/adapter>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|クラス|説明|
|-----------|-----------------|
|[collection_adapter (STL/CLR)](#collection_adapter)|基本クラスライブラリ (BCL) コレクションを範囲としてラップします。|
|[range_adapter (STL/CLR)](#range_adapter)|範囲を BCL コレクションとしてラップします。|

|機能|説明|
|--------------|-----------------|
|[make_collection (STL/CLR)](#make_collection)|反復子ペアを使用して範囲アダプターを作成します。|

## <a name="members"></a>メンバー

## <a name="collection_adapter-stlclr"></a><a name="collection_adapter"></a> collection_adapter (STL/CLR)

STL/CLR コンテナーとして使用するために .NET コレクションをラップします。 `collection_adapter`は、単純な STL/CLR コンテナーオブジェクトを記述するテンプレートクラスです。 これは、基本クラスライブラリ (BCL) インターフェイスをラップし、被制御シーケンスを操作するために使用する反復子ペアを返します。

### <a name="syntax"></a>構文

```cpp
template<typename Coll>
    ref class collection_adapter;

template<>
    ref class collection_adapter<
        System::Collections::ICollection>;
template<>
    ref class collection_adapter<
        System::Collections::IEnumerable>;
template<>
    ref class collection_adapter<
        System::Collections::IList>;
template<>
    ref class collection_adapter<
        System::Collections::IDictionary>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::ICollection<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IEnumerable<Value>>;
template<typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IList<Value>>;
template<typename Key,
    typename Value>
    ref class collection_adapter<
        System::Collections::Generic::IDictionary<Key, Value>>;
```

#### <a name="parameters"></a>パラメーター

*Coll*<br/>
ラップされたコレクションの型。

### <a name="specializations"></a>特殊化

|特殊化|説明|
|--------------------|-----------------|
|IEnumerable|要素をシーケンス処理します。|
|ICollection|要素のグループを保持します。|
|IList|要素の順序付けられたグループを保持します。|
|IDictionary|{Key, value} のペアのセットを保持します。|
|IEnumerable\<Value>|型指定された要素を通じてシーケンス処理を行います。|
|ICollection\<Value>|型指定された要素のグループを保持します。|
|IList\<Value>|型指定された要素の順序付けられたグループを保持します。|
|IDictionary\<Value> |型指定された {key, value} のペアのセットを保持します。|

### <a name="members"></a>メンバー

|型の定義|説明|
|---------------------|-----------------|
|[collection_adapter::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[collection_adapter::iterator (STL/CLR)](#iterator)|被制御シーケンスの反復子の型です。|
|[collection_adapter::key_type (STL/CLR)](#key_type)|ディクショナリキーの型。|
|[collection_adapter::mapped_type (STL/CLR)](#mapped_type)|ディクショナリ値の型。|
|[collection_adapter::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[collection_adapter::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[collection_adapter::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[collection_adapter::base (STL/CLR)](#base)|ラップされた BCL インターフェイスを指定します。|
|[collection_adapter::begin (STL/CLR)](#begin)|被制御シーケンスの先頭を指定します。|
|[collection_adapter::collection_adapter (STL/CLR)](#collection_adapter_collection_adapter)|アダプターオブジェクトを構築します。|
|[collection_adapter::end (STL/CLR)](#end)|被制御シーケンスの末尾を指定します。|
|[collection_adapter::size (STL/CLR)](#size)|要素の数をカウントします。|
|[collection_adapter::swap (STL/CLR)](#swap)|2 つのコンテナーのコンテンツを交換します。|

|演算子|説明|
|--------------|-----------------|
|[collection_adapter::operator= (STL/CLR)](#op_eq)|格納されている BCL ハンドルを置き換えます。|

### <a name="remarks"></a>解説

このテンプレートクラスを使用して、BCL コンテナーを STL/CLR コンテナーとして操作します。 は、 `collection_adapter` BCL インターフェイスへのハンドルを格納します。これは、要素のシーケンスを制御します。 オブジェクトは、 `collection_adapter` `X` 要素に `X.begin()` `X.end()` 順番にアクセスするために使用する入力反復子のペアを返します。 また、一部の特殊化では、 `X.size()` 被制御シーケンスの長さを決定するためにも記述できます。

## <a name="collection_adapterbase-stlclr"></a><a name="base"></a> collection_adapter:: base (STL/CLR)

ラップされた BCL インターフェイスを指定します。

### <a name="syntax"></a>構文

```cpp
Coll^ base();
```

### <a name="remarks"></a>解説

このメンバー関数は、格納されている BCL インターフェイスハンドルを返します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_base.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Console::WriteLine("base() same = {0}", c1.base() == %c1);
    return (0);
    }
```

```Output
x x x x x x
base() same = True
```

## <a name="collection_adapterbegin-stlclr"></a><a name="begin"></a> collection_adapter:: begin (STL/CLR)

被制御シーケンスの先頭を指定します。

### <a name="syntax"></a>構文

```cpp
iterator begin();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素、または空のシーケンスの末尾の次の位置を指定する入力反復子を返します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_begin.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect first two items
    Mycoll::iterator it = c1.begin();
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

## <a name="collection_adaptercollection_adapter-stlclr"></a><a name="collection_adapter_collection_adapter"></a> collection_adapter:: collection_adapter (STL/CLR)

アダプターオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
collection_adapter();
collection_adapter(collection_adapter<Coll>% right);
collection_adapter(collection_adapter<Coll>^ right);
collection_adapter(Coll^ collection);
```

#### <a name="parameters"></a>パラメーター

*表す*<br/>
ラップする BCL ハンドル。

*そうです*<br/>
コピーするオブジェクト。

### <a name="remarks"></a>解説

コンストラクター:

`collection_adapter();`

で格納されているハンドルを初期化 **`nullptr`** します。

コンストラクター:

`collection_adapter(collection_adapter<Coll>% right);`

`right.` [collection_adapter:: BASE (STL/CLR)](#base)を使用して、格納されているハンドルを初期化 `()` します。

コンストラクター:

`collection_adapter(collection_adapter<Coll>^ right);`

`right->` [collection_adapter:: BASE (STL/CLR)](#base)を使用して、格納されているハンドルを初期化 `()` します。

コンストラクター:

`collection_adapter(Coll^ collection);`

で格納されているハンドルを初期化 `collection` します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');

    // construct an empty container
    Mycoll c1;
    System::Console::WriteLine("base() null = {0}", c1.base() == nullptr);

    // construct with a handle
    Mycoll c2(%d6x);
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mycoll c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying a container handle
    Mycoll c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
base() null = True
x x x x x x
x x x x x x
x x x x x x
```

## <a name="collection_adapterdifference_type-stlclr"></a><a name="difference_type"></a> collection_adapter::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、署名された要素の数を表します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_difference_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mycoll::difference_type diff = 0;
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        ++diff;
    System::Console::WriteLine("end()-begin() = {0}", diff);
    return (0);
}
```

```Output
a b c
end()-begin() = 3
```

## <a name="collection_adapterend-stlclr"></a><a name="end"></a> collection_adapter:: end (STL/CLR)

被制御シーケンスの末尾を指定します。

### <a name="syntax"></a>構文

```cpp
iterator end();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾の次の位置を指し示す入力反復子を返します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_end.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapteriterator-stlclr"></a><a name="iterator"></a> collection_adapter:: iterator (STL/CLR)

被制御シーケンスの反復子の型です。

### <a name="syntax"></a>構文

```cpp
typedef T1 iterator;
```

### <a name="remarks"></a>解説

この型は、 `T1` 被制御シーケンスの入力反復子として使用できる未指定の型のオブジェクトを表します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_iterator.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
        System::Console::Write("{0} ", *it);
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adapterkey_type-stlclr"></a><a name="key_type"></a> collection_adapter:: key_type (STL/CLR)

ディクショナリキーの型。

### <a name="syntax"></a>構文

```cpp
typedef Key key_type;
```

### <a name="remarks"></a>解説

この型は、またはの特殊化のテンプレートパラメーターのシノニムです。それ以外の場合は、定義され `Key` `IDictionary` `IDictionary<Value>` ません。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_key_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adaptermapped_type-stlclr"></a><a name="mapped_type"></a> collection_adapter:: mapped_type (STL/CLR)

ディクショナリ値の型。

### <a name="syntax"></a>構文

```cpp
typedef Value mapped_type;
```

### <a name="remarks"></a>解説

この型は、またはの特殊化のテンプレートパラメーターのシノニムです。それ以外の場合は、定義され `Value` `IDictionary` `IDictionary<Value>` ません。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_mapped_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/map>

typedef cliext::map<wchar_t, int> Mymap;
typedef cliext::collection_adapter<
    System::Collections::Generic::IDictionary<wchar_t, int>> Mycoll;
typedef System::Collections::Generic::KeyValuePair<wchar_t,int> Mypair;
int main()
{
    Mymap d1;
    d1.insert(Mymap::make_value(L'a', 1));
    d1.insert(Mymap::make_value(L'b', 2));
    d1.insert(Mymap::make_value(L'c', 3));
    Mycoll c1(%d1);

    // display contents "[a 1] [b 2] [c 3] "
    for each (Mypair elem in c1)
    {
        Mycoll::key_type key = elem.Key;
        Mycoll::mapped_type value = elem.Value;
        System::Console::Write("[{0} {1}] ", key, value);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
[a 1] [b 2] [c 3]
```

## <a name="collection_adapteroperator-stlclr"></a><a name="op_eq"></a> collection_adapter:: operator = (STL/CLR)

格納されている BCL ハンドルを置き換えます。

### <a name="syntax"></a>構文

```cpp
collection_adapter<Coll>% operator=(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするアダプター。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 このメソッドを使用して、格納されている BCL ハンドルを *右側* の格納されている bcl ハンドルのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_operator_as.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mycoll c2;
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

## <a name="collection_adapterreference-stlclr"></a><a name="reference"></a> collection_adapter:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_reference.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
    {
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents "a b c "
    Mycoll::iterator it = c1.begin();
    for (; it != c1.end(); ++it)
    {   // get a reference to an element
        Mycoll::reference ref = *it;
        System::Console::Write("{0} ", ref);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="collection_adaptersize-stlclr"></a><a name="size"></a> collection_adapter:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 またはの特殊化では定義されていません `IEnumerable` `IEnumerable<Value>` 。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_size.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x "
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adaptersize_type-stlclr"></a><a name="size_type"></a> collection_adapter:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_size_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d6x(6, L'x');
    Mycoll c1(%d6x);

    // display initial contents "x x x x x x"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    Mycoll::size_type size = c1.size();
    System::Console::WriteLine("size() = {0}", size);
    return (0);
}
```

```Output
x x x x x x
size() = 6
```

## <a name="collection_adapterswap-stlclr"></a><a name="swap"></a> collection_adapter:: swap (STL/CLR)

2 つのコンテナーのコンテンツを交換します。

### <a name="syntax"></a>構文

```cpp
void swap(collection_adapter<Coll>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するコンテナー。

### <a name="remarks"></a>解説

このメンバー関数は、格納されている BCL ハンドルをとの間で交換し **`*this`** ます。 

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_swap.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display initial contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct another container with repetition of values
    cliext::deque<wchar_t> d2(5, L'x');
    Mycoll c2(%d2);
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

## <a name="collection_adaptervalue_type-stlclr"></a><a name="value_type"></a> collection_adapter:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、特殊化に存在する場合は、テンプレートパラメーター *値* のシノニムです。それ以外の場合は、のシノニムになり `System::Object^` ます。

### <a name="example"></a>例

```cpp
// cliext_collection_adapter_value_type.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::collection_adapter<
    System::Collections::ICollection> Mycoll;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Mycoll c1(%d1);

    // display contents "a b c" using value_type
    for (Mycoll::iterator it = c1.begin();
        it != c1.end(); ++it)
    {   // store element in value_type object
        Mycoll::value_type val = *it;

        System::Console::Write("{0} ", val);
    }
    System::Console::WriteLine();
    return (0);
}
```

```Output
a b c
```

## <a name="make_collection-stlclr"></a><a name="make_collection"></a> make_collection (STL/CLR)

`range_adapter`反復子ペアからを作成します。

### <a name="syntax"></a>構文

```cpp
template<typename Iter>
    range_adapter<Iter> make_collection(Iter first, Iter last);
```

#### <a name="parameters"></a>パラメーター

*Iter*<br/>
ラップされた反復子の型。

*first*<br/>
ラップする最初の反復子。

*last*<br/>
ラップする2番目の反復子。

### <a name="remarks"></a>解説

このテンプレート関数は `gcnew range_adapter<Iter>(first, last)` を返します。 このメソッドを使用して、 `range_adapter<Iter>` 1 組の反復子からオブジェクトを構築します。

### <a name="example"></a>例

```cpp
// cliext_make_collection.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // display contents " a b c"
    for each (wchar_t elem in d1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    System::Collections::ICollection^ p1 =
        cliext::make_collection(d1.begin(), d1.end());
    System::Console::WriteLine("Count = {0}", p1->Count);
    System::Console::WriteLine("IsSynchronized = {0}",
        p1->IsSynchronized);
    System::Console::WriteLine("SyncRoot not nullptr = {0}",
        p1->SyncRoot != nullptr);

    // copy the sequence
    cli::array<System::Object^>^ a1 = gcnew cli::array<System::Object^>(5);

    a1[0] = L'|';
    p1->CopyTo(a1, 1);
    a1[4] = L'|';
    for each (wchar_t elem in a1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
Count = 3
IsSynchronized = False
SyncRoot not nullptr = True
| a b c |
```

## <a name="range_adapter-stlclr"></a><a name="range_adapter"></a> range_adapter (STL/CLR)

複数の基本クラスライブラリ (BCL) インターフェイスを実装するために使用される反復子のペアをラップするテンプレートクラス。 Range_adapter を使用して、STL/CLR 範囲を BCL コレクションのように操作します。

### <a name="syntax"></a>構文

```cpp
template<typename Iter>
    ref class range_adapter
        :   public
        System::Collections::IEnumerable,
        System::Collections::ICollection,
        System::Collections::Generic::IEnumerable<Value>,
        System::Collections::Generic::ICollection<Value>
    { ..... };
```

#### <a name="parameters"></a>パラメーター

*Iter*<br/>
ラップされた反復子に関連付けられた型。

### <a name="members"></a>メンバー

|メンバー関数|説明|
|---------------------|-----------------|
|[range_adapter::range_adapter (STL/CLR)](#range_adapter_range_adapter)|アダプターオブジェクトを構築します。|

|演算子|説明|
|--------------|-----------------|
|[range_adapter::operator= (STL/CLR)](#range_adapter_op_eq)|格納されている反復子のペアを置き換えます。|

### <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.Collections.IEnumerable>|コレクション内の要素を反復処理します。|
|<xref:System.Collections.ICollection>|要素のグループを保持します。|
|<xref:System.Collections.Generic.IEnumerable%601>|コレクション内の型指定された要素を反復処理します。|
|<xref:System.Collections.Generic.ICollection%601>|型指定された要素のグループを保持します。|

### <a name="remarks"></a>解説

Range_adapter は、要素のシーケンスを区切る反復子のペアを格納します。 オブジェクトには、要素を順番に反復処理できる4つの BCL インターフェイスが実装されています。 このテンプレートクラスを使用して、BCL コンテナーと同じように STL/CLR 範囲を操作します。

## <a name="range_adapteroperator-stlclr"></a><a name="range_adapter_op_eq"></a> range_adapter:: operator = (STL/CLR)

格納されている反復子のペアを置き換えます。

### <a name="syntax"></a>構文

```cpp
range_adapter<Iter>% operator=(range_adapter<Iter>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするアダプター。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 このメソッドを使用して、格納されている反復子ペアを *右* の格納されている反復子ペアのコピーに置き換えることができます。

### <a name="example"></a>例

```cpp
// cliext_range_adapter_operator_as.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');
    Myrange c1(d1.begin(), d1.end());

    // display contents " a b c"
    for each (wchar_t elem in c1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Myrange c2;
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

## <a name="range_adapterrange_adapter-stlclr"></a><a name="range_adapter_range_adapter"></a> range_adapter:: range_adapter (STL/CLR)

アダプターオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
range_adapter();
range_adapter(range_adapter<Iter>% right);
range_adapter(range_adapter<Iter>^ right);
range_adapter(Iter first, Iter last);
```

#### <a name="parameters"></a>パラメーター

*first*<br/>
ラップする最初の反復子。

*last*<br/>
ラップする2番目の反復子。

*そうです*<br/>
コピーするオブジェクト。

### <a name="remarks"></a>解説

コンストラクター:

`range_adapter();`

既定の構築反復子を使用して、格納された反復子ペアを初期化します。

コンストラクター:

`range_adapter(range_adapter<Iter>% right);`

*右側* に格納されているペアをコピーすることによって、格納された反復子ペアを初期化します

コンストラクター:

`range_adapter(range_adapter<Iter>^ right);`

に格納されているペアをコピーすることにより、格納された反復子ペアを初期化し `*right` ます。

コンストラクター:

`range_adapter(Iter^ first, last);`

*最初* と *最後* の、格納されている反復子のペアを初期化します。

### <a name="example"></a>例

```cpp
// cliext_range_adapter_construct.cpp
// compile with: /clr
#include <cliext/adapter>
#include <cliext/deque>

typedef cliext::deque<wchar_t> Mycont;
typedef cliext::range_adapter<Mycont::iterator> Myrange;
int main()
{
    cliext::deque<wchar_t> d1;
    d1.push_back(L'a');
    d1.push_back(L'b');
    d1.push_back(L'c');

    // construct an empty adapter
    Myrange c1;

    // construct with an iterator pair
    Myrange c2(d1.begin(), d1.end());
    for each (wchar_t elem in c2)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another adapter
    Myrange c3(c2);
    for each (wchar_t elem in c3)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying an adapter handle
    Myrange c4(%c3);
    for each (wchar_t elem in c4)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
}
```

```Output
a b c
a b c
a b c
```
