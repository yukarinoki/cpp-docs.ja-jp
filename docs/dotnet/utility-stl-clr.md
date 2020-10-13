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
ms.openlocfilehash: faf7f607f9433fa3e4813957b24220a5e66e1e49
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008620"
---
# <a name="utility-stlclr"></a>utility (STL/CLR)

`<cliext/utility>`テンプレートクラス `pair` といくつかのサポートテンプレート関数を定義するには、STL/CLR ヘッダーを含めます。

## <a name="syntax"></a>構文

```cpp
#include <utility>
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/utility>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|クラス|説明|
|-----------|-----------------|
|[pair (STL/CLR)](#pair)|要素のペアをラップします。|

|演算子|説明|
|--------------|-----------------|
|[operator = = (pair) (STL/CLR)](#op_eq)|ペアが等しいかどうかの比較。|
|[operator! = (pair) (STL/CLR)](#op_neq)|ペアが等しくないかどうかの比較。|
|[演算子< (ペア) (STL/CLR)](#op_lt)|対が比較より小さい。|
|[operator \< = (pair) (STL/CLR)](#op_lteq)|ペア以下の比較。|
|[演算子> (ペア) (STL/CLR)](#op_gt)|対が比較を超えています。|
|[operator>= (pair) (STL/CLR)](#op_gteq)|対以上の比較。|

|機能|説明|
|--------------|-----------------|
|[make_pair (STL/CLR)](#make_pair)|値のペアからペアを作成します。|

## <a name="pair-stlclr"></a><a name="pair"></a> pair (STL/CLR)

このテンプレートクラスは、値のペアをラップするオブジェクトを表します。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    ref class pair;
```

#### <a name="parameters"></a>パラメーター

*Value1*<br/>
最初にラップされた値の型。

*Value2*<br/>
2番目にラップされた値の型。

## <a name="members"></a>メンバー

|型の定義|説明|
|---------------------|-----------------|
|[pair::first_type (STL/CLR)](#first_type)|最初にラップされた値の型。|
|[pair::second_type (STL/CLR)](#second_type)|2番目にラップされた値の型。|

|メンバーオブジェクト|説明|
|-------------------|-----------------|
|[pair::first (STL/CLR)](#first)|最初に格納された値。|
|[pair::second (STL/CLR)](#second)|2番目に格納された値。|

|メンバー関数|説明|
|---------------------|-----------------|
|[pair::pair (STL/CLR)](#pair_pair)|ペアオブジェクトを構築します。|
|[pair::swap (STL/CLR)](#swap)|2つのペアの内容を交換します。|

|演算子|説明|
|--------------|-----------------|
|[pair::operator= (STL/CLR)](#op_as)|格納されている値のペアを置き換えます。|

## <a name="remarks"></a>解説

オブジェクトは、値のペアを格納します。 このテンプレートクラスを使用して、2つの値を1つのオブジェクトに結合します。 また、オブジェクト `cliext::pair` (ここで説明) はマネージ型のみを格納します。アンマネージ型のペアを格納するには `std::pair` 、で宣言 `<utility>` します。

## <a name="pairfirst-stlclr"></a><a name="first"></a> pair:: first (STL/CLR)

最初にラップされた値。

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

## <a name="pairfirst_type-stlclr"></a><a name="first_type"></a> pair:: first_type (STL/CLR)

最初にラップされた値の型。

### <a name="syntax"></a>構文

```cpp
typedef Value1 first_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター *Value1*のシノニムです。

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

## <a name="pairoperator-stlclr"></a><a name="op_as"></a> pair:: operator = (STL/CLR)

格納されている値のペアを置き換えます。

### <a name="syntax"></a>構文

```cpp
pair<Value1, Value2>% operator=(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするペア。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 格納されている値のペアを、格納され *ている値*のペアのコピーに置き換えるために使用します。

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

## <a name="pairpair-stlclr"></a><a name="pair_pair"></a> ペア: エア:p (STL/CLR)

ペアオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
pair();
pair(pair<Coll>% right);
pair(pair<Coll>^ right);
pair(Value1 val1, Value2 val2);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
ストアにペアリングします。

*val1*<br/>
格納する最初の値。

*val2*<br/>
格納する2番目の値。

### <a name="remarks"></a>解説

コンストラクター:

`pair();`

既定の構築値を使用して、格納されているペアを初期化します。

コンストラクター:

`pair(pair<Value1, Value2>% right);`

`right.`[ペア:: FIRST (STL/clr)](#first)と `right.` [PAIR:: second (stl/clr)](#second)を使用して、格納されているペアを初期化します。

`pair(pair<Value1, Value2>^ right);`

`right->`[ペア:: FIRST (STL/clr)](#first)と `right>` [PAIR:: second (stl/clr)](#second)を使用して、格納されているペアを初期化します。

コンストラクター:

`pair(Value1 val1, Value2 val2);`

*val1*と*val2*を使用して、格納されているペアを初期化します。

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

## <a name="pairsecond-stlclr"></a><a name="second"></a> pair:: second (STL/CLR)

2番目にラップされた値。

### <a name="syntax"></a>構文

```cpp
Value2 second;
```

### <a name="remarks"></a>解説

オブジェクトは、2番目のラップされた値を格納します。

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

## <a name="pairsecond_type-stlclr"></a><a name="second_type"></a> pair:: second_type (STL/CLR)

2番目にラップされた値の型。

### <a name="syntax"></a>構文

```cpp
typedef Value2 second_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター *Value2*のシノニムです。

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

## <a name="pairswap-stlclr"></a><a name="swap"></a> pair:: swap (STL/CLR)

2つのペアの内容を交換します。

### <a name="syntax"></a>構文

```cpp
void swap(pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コンテンツのスワップに使用するペア。

### <a name="remarks"></a>解説

このメンバー関数は、との間に格納されている値のペアを交換し **`*this`** ます。 *right*

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

## <a name="make_pair-stlclr"></a><a name="make_pair"></a> make_pair (STL/CLR)

`pair`値のペアからを作成します。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    pair<Value1, Value2> make_pair(Value1 first, Value2 second);
```

#### <a name="parameters"></a>パラメーター

*Value1*<br/>
最初にラップされた値の型。

*Value2*<br/>
2番目にラップされた値の型。

*first*<br/>
ラップする最初の値。

*second*<br/>
2番目に折り返す値。

### <a name="remarks"></a>解説

このテンプレート関数は `pair<Value1, Value2>(first, second)` を返します。 値のペアからオブジェクトを構築するために使用し `pair<Value1, Value2>` ます。

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

## <a name="operator-pair-stlclr"></a><a name="op_neq"></a> operator! = (pair) (STL/CLR)

ペアが等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator!=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left == right)` ます。 このメソッドを使用して、2つのペアが要素ごとに比較されるときに、 *left* が *right* と同じ順序で並んでいないかどうかをテストします。

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lt"></a> 演算子 &lt; (pair) (STL/CLR)

対が比較より小さい。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator<(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `left.first <` `right.first || !(right.first <` `left.first &&` `left.second <` `right.second` ます。 このメソッドを使用して、2つのペアが要素ごとに比較されたときに、 *left* が *右* に並んでいるかどうかをテストします。

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

## <a name="operatorlt-pair-stlclr"></a><a name="op_lteq"></a> operator &lt; = (pair) (STL/CLR)

ペア以下の比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator<=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `!(right < left)` ます。 このメソッドを使用して、2つのペアが要素ごとに比較されたときに、 *right*の後に*left*が順序付けされていないかどうかをテストします。

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

## <a name="operator-pair-stlclr"></a><a name="op_eq"></a> operator = = (pair) (STL/CLR)

ペアが等しいかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator==(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `left.first ==` `right.first &&` `left.second ==` `right.second` ます。 このメソッドを使用して、2つのペアが要素ごとに比較された場合に、 *left* が *right* と同じであるかどうかをテストします。

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gt"></a> 演算子 &gt; (pair) (STL/CLR)

対が比較を超えています。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator>(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `right` `<` `left` ます。 このメソッドを使用して、2つのペアが要素によって比較されたときに、*右側*の順序が並べ替えられて*いるかどう*かをテストします。

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

## <a name="operatorgt-pair-stlclr"></a><a name="op_gteq"></a> operator &gt; = (pair) (STL/CLR)

対以上の比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value1,
    typename Value2>
    bool operator>=(pair<Value1, Value2>% left,
        pair<Value1, Value2>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のペア。

*そうです*<br/>
比較する右のペア。

### <a name="remarks"></a>解説

演算子関数はを返し `!(left < right)` ます。 このメソッドを使用して、2つのペアが要素ごとに比較されるときに、 *left* が *right* の前に順序付けされていないかどうかをテストします。

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
