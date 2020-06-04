---
title: utility (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/utility>
- cliext::pair
- cliext::pair::pair
- cliext::pair::first
- cliext::pair::first_type
- cliext::pair::second
- cliext::pair::second_type
- cliext::pair::swap
- cliext::make_pair
- cliext::pair::operator=
- cliext::pair::operator==
- cliext::pair::operator>=
- cliext::pair::operator>
- cliext::pair::operator!=
- cliext::pair::operator<=
- cliext::pair::operator<
helpviewer_keywords:
- <utility> header [STL/CLR]
- utility header [STL/CLR]
- <cliext/utility> header [STL/CLR]
- first member [STL/CLR]
- first_type member [STL/CLR]
- second member [STL/CLR]
- second_type member [STL/CLR]
- swap member [STL/CLR]
- make_pair function [STL/CLR]
- pair class [STL/CLR]
- pair member [STL/CLR]
- operator== member [STL/CLR]
- operator= member [STL/CLR]
- operator>= member [STL/CLR]
- operator> member [STL/CLR]
- operator!= member [STL/CLR]
- operator<= member [STL/CLR]
- operator< member [STL/CLR]
ms.assetid: fb48cb75-d5ef-47ce-b526-bf60dc86c552
ms.openlocfilehash: 6d025230abcff42e367a231e616a13f0f8c684f0
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320291"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

テンプレート クラス`pair`といくつかのサポート`<cliext/utility>`テンプレート関数を定義する STL/CLR ヘッダーを含めます。

## <a name="syntax"></a>構文

```cpp
#include <utility>
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<クライト/ユーティリティ>

**名前空間:** クエクスキ

## <a name="declarations"></a>宣言

|クラス|説明|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|要素のペアをラップします。|

|演算子|説明|
|--------------|-----------------|
|[演算子==(ペア)(STL/CLR)](#op_eq)|対等比較。|
|[演算子!= (ペア) (STL/CLR)](#op_neq)|ペアは等しくない比較です。|
|[演算子< (ペア) (STL/CLR)](#op_lt)|比較より小さいペア。|
|[演算子\<= (ペア) (STL/CLR)](#op_lteq)|比較の値以下のペア。|
|[演算子> (ペア) (STL/CLR)](#op_gt)|比較より大きいペア。|
|[operator>= (pair) (STL/CLR)](#op_gteq)|比較の値が大きいか等しいかのペアです。|

|機能|説明|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|値のペアからペアを作成します。|

## <a name="members"></a>メンバー

## <a name="pair-stlclr"></a><a name="pair"></a>ペア (STL/CLR)

テンプレート クラスは、値のペアをラップするオブジェクトを表します。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>パラメーター

*値1*<br/>
最初にラップされた値の型。

*Value2*<br/>
2 番目にラップされた値の型。

## <a name="members"></a>メンバー

|型定義|説明|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|最初にラップされた値の型。|
|[pair::second_type (STL/CLR)](#second_type)|2 番目のラップされた値の型。|

|メンバー オブジェクト|説明|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|最初に格納された値。|
|[pair::second (STL/CLR)](#second)|2 番目の格納値。|

|メンバー関数|説明|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|ペア オブジェクトを構築します。|
|[pair::swap (STL/CLR)](#swap)|2 つのペアの内容を入れ替えます。|

|演算子|説明|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|格納されている値のペアを置き換えます。|

## <a name="remarks"></a>解説

オブジェクトは、値のペアを格納します。 このテンプレート クラスを使用して、2 つの値を 1 つのオブジェクトに結合します。 また、オブジェクト`cliext::pair`(ここで説明) はマネージ型のみを格納します。アンマネージ型のペアを格納するには`std::pair`、 で宣言`<utility>`されています。

## <a name="pairfirst-stlclr"></a><a name="first"></a>ペア::最初(STL/CLR)

最初のラップされた値。

### <a name="syntax"></a>構文

```cpp
Value1 first;
```

### <a name="remarks"></a>解説

オブジェクトは、最初にラップされた値を格納します。

### <a name="example"></a>例

```cpp
// cliext_pair_first.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a>ペア::first_type (STL/CLR)

最初にラップされた値の型。

### <a name="syntax"></a>構文

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメータ*Value1*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_pair_first_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairoperator-stlclr"></a><a name="op_as"></a>ペア::演算子=(STL/CLR)

格納されている値のペアを置き換えます。

### <a name="syntax"></a>構文

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするペア。

### <a name="remarks"></a>解説

メンバ オペレータは*オブジェクトに右*をコピーし、`*this`を返します。 この値を使用して、格納されている値のペアを *、右*に格納されている値のペアのコピーに置き換えます。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_as.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

// assign to a new pair
    cliext::pair<wchar_t, int> c2;
    c2 = c1;
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);
    return (0);
    }
```

```Output
[x, 3]
[x, 3]
```

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a>ペア::pエア(STL/CLR)

ペア オブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
保存するペア。

*val1*<br/>
格納する最初の値。

*val2*<br/>
格納する 2 番目の値。

### <a name="remarks"></a>解説

コンストラクター:

`pair();`

は、デフォルトの構築値を使用して、格納されたペアを初期化します。

コンストラクター:

`pair(pair<Value1, Value2>% right);`

は、ペア`right.`[::最初 (STL/CLR)](../dotnet/pair-first-stl-clr.md)と`right.`[ペア::秒 (STL/CLR)](../dotnet/pair-second-stl-clr.md)で格納されたペアを初期化します。

`pair(pair<Value1, Value2>^ right);`

は、ペア`right->`[::最初 (STL/CLR)](../dotnet/pair-first-stl-clr.md)と`right>`[ペア::秒 (STL/CLR)](../dotnet/pair-second-stl-clr.md)で格納されたペアを初期化します。

コンストラクター:

`pair(Value1 val1, Value2 val2);`

は、格納されたペアを*val1*および*val2*で初期化します。

### <a name="example"></a>例

```cpp
// cliext_pair_construct.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
// construct an empty container
    cliext::pair<wchar_t, int> c1;
    System::Console::WriteLine("[{0}, {1}]",
        c1.first == L'\0' ? "\\0" : "??", c1.second);

// construct with a pair of values
    cliext::pair<wchar_t, int> c2(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

// construct by copying another pair
    cliext::pair<wchar_t, int> c3(c2);
    System::Console::WriteLine("[{0}, {1}]", c3.first, c3.second);

// construct by copying a pair handle
    cliext::pair<wchar_t, int> c4(%c3);
    System::Console::WriteLine("[{0}, {1}]", c4.first, c4.second);

    return (0);
    }
```

```Output
[\0, 0]
[x, 3]
[x, 3]
[x, 3]
```

## <a name="pairsecond-stlclr"></a><a name="second"></a>ペア::2番目(STL/CLR)

2 番目のラップされた値。

### <a name="syntax"></a>構文

```cpp
Value2 second;
```

### <a name="remarks"></a>解説

オブジェクトは、2 番目のラップされた値を格納します。

### <a name="example"></a>例

```cpp
// cliext_pair_second.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a>ペア::second_type (STL/CLR)

2 番目のラップされた値の型。

### <a name="syntax"></a>構文

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメータ*Value2*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_pair_second_type.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    cliext::pair<wchar_t, int>::first_type first_val = c1.first;
    cliext::pair<wchar_t, int>::second_type second_val = c1.second;
    System::Console::WriteLine("[{0}, {1}]", first_val, second_val);
    return (0);
    }
```

```Output
[x, 3]
```

## <a name="pairswap-stlclr"></a><a name="swap"></a>ペア::スワップ(STL/CLR)

2 つのペアの内容を入れ替えます。

### <a name="syntax"></a>構文

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツを交換するペア。

### <a name="remarks"></a>解説

メンバー関数は、 と`*this`*の*間で格納された値のペアを入れ替えます。

### <a name="example"></a>例

```cpp
// cliext_pair_swap.cpp
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

## <a name="make_pair-stlclr"></a><a name="make_pair"></a>make_pair (STL/CLR)

値の`pair`ペアからを作成します。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>パラメーター

*値1*<br/>
最初にラップされた値の型。

*Value2*<br/>
2 番目のラップされた値の型。

*first*<br/>
ラップする最初の値。

*second*<br/>
ラップする 2 番目の値。

### <a name="remarks"></a>解説

このテンプレート関数は `pair<Value1, Value2>(first, second)` を返します。 この値を使用して、`pair<Value1, Value2>`値のペアからオブジェクトを作成します。

### <a name="example"></a>例

```cpp
// cliext_make_pair.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);

    c1 = cliext::make_pair(L'y', 4);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    return (0);
    }
```

```Output
[x, 3]
[y, 4]
```

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a>演算子!= (ペア) (STL/CLR)

ペアは等しくない比較です。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`!(left == right)`を返します。 2 つのペアが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_ne.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] != [x 3] is {0}",
        c1 != c1);
    System::Console::WriteLine("[x 3] != [x 4] is {0}",
        c1 != c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] != [x 3] is False
[x 3] != [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a>演算子&lt;(ペア) (STL/CLR)

比較より小さいペア。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`left.first <``right.first || !(right.first <``left.first &&``left.second <``right.second`を返します。 2 つのペアが要素ごとに比較されるときに *、left*が*右*前に並べ替えられたかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_lt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] < [x 3] is {0}",
        c1 < c1);
    System::Console::WriteLine("[x 3] < [x 4] is {0}",
        c1 < c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] < [x 3] is False
[x 3] < [x 4] is True
```

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a>演算子&lt;= (ペア) (STL/CLR)

比較の値以下のペア。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`!(right < left)`を返します。 2 つのペアが要素*left*ごとに比較される場合、*左が右*の後に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_le.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] <= [x 3] is {0}",
        c1 <= c1);
    System::Console::WriteLine("[x 4] <= [x 3] is {0}",
        c2 <= c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] <= [x 3] is True
[x 4] <= [x 3] is False
```

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a>演算子==(ペア)(STL/CLR)

対等比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`left.first ==``right.first &&``left.second ==``right.second`を返します。 2 つのペアが要素ごとに比較される場合、*左*が*右*と同じ順序で並べられるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_eq.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] == [x 3] is {0}",
        c1 == c1);
    System::Console::WriteLine("[x 3] == [x 4] is {0}",
        c1 == c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] == [x 3] is True
[x 3] == [x 4] is False
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a>演算子&gt;(ペア) (STL/CLR)

比較より大きいペア。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`right``<``left`を返します。 2 つのペアが要素ごとに比較されるときに *、左*が*右*の後に並べ替えられたかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_gt.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] > [x 3] is {0}",
        c1 > c1);
    System::Console::WriteLine("[x 4] > [x 3] is {0}",
        c2 > c1);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] > [x 3] is False
[x 4] > [x 3] is True
```

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a>演算子&gt;= (ペア) (STL/CLR)

比較の値が大きいか等しいかのペアです。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数は、`!(left < right)`を返します。 2 つのペアが要素*left*ごとに比較される場合、*左が右*より前に並べられていないかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_pair_operator_ge.cpp
// compile with: /clr
#include <cliext/utility>

int main()
    {
    cliext::pair<wchar_t, int> c1(L'x', 3);
    System::Console::WriteLine("[{0}, {1}]", c1.first, c1.second);
    cliext::pair<wchar_t, int> c2(L'x', 4);
    System::Console::WriteLine("[{0}, {1}]", c2.first, c2.second);

    System::Console::WriteLine("[x 3] >= [x 3] is {0}",
        c1 >= c1);
    System::Console::WriteLine("[x 3] >= [x 4] is {0}",
        c1 >= c2);
    return (0);
    }
```

```Output
[x, 3]
[x, 4]
[x 3] >= [x 3] is True
[x 3] >= [x 4] is False
```
