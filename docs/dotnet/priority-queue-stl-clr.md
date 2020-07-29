---
title: priority_queue (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::priority_queue
- cliext::priority_queue::assign
- cliext::priority_queue::const_reference
- cliext::priority_queue::container_type
- cliext::priority_queue::difference_type
- cliext::priority_queue::empty
- cliext::priority_queue::generic_container
- cliext::priority_queue::generic_value
- cliext::priority_queue::get_container
- cliext::priority_queue::operator=
- cliext::priority_queue::pop
- cliext::priority_queue::priority_queue
- cliext::priority_queue::push
- cliext::priority_queue::reference
- cliext::priority_queue::size
- cliext::priority_queue::size_type
- cliext::priority_queue::to_array
- cliext::priority_queue::top
- cliext::priority_queue::top_item
- cliext::priority_queue::value_comp
- cliext::priority_queue::value_compare
- cliext::priority_queue::value_type
helpviewer_keywords:
- priority_queue class [STL/CLR]
- <queue> header [STL/CLR]
- <cliext/queue> header [STL/CLR]
- assign member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- priority_queue member [STL/CLR]
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_comp member [STL/CLR]
- value_compare member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 4d0000d3-68ff-4c4b-8157-7060540136f5
ms.openlocfilehash: 6c5a37cc76f6ac3a3f92cf54b440960d7476daa9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211036"
---
# <a name="priority_queue-stlclr"></a>priority_queue (STL/CLR)

このテンプレートクラスは、アクセスが制限されている要素のさまざまな長さの順序付け順序を制御するオブジェクトを表します。 コンテナーアダプターは、 `priority_queue` 基になるコンテナーを優先順位キューとして管理するために使用します。

次の説明で、 `GValue` は、後者が参照型である場合を除き、*値*と同じです。この場合、は `Value^` です。 同様に、 `GContainer` は、後者が参照型である場合を除き、*コンテナー*と同じです。この場合、は `Container^` です。

## <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    ref class priority_queue
        System::ICloneable,
        Microsoft::VisualC::StlClr::IPriorityQueue<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*Value*<br/>
被制御シーケンス内の要素の型。

*コンテナー*<br/>
基になるコンテナーの型。

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/queue>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型の定義|説明|
|---------------------|-----------------|
|[priority_queue::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[priority_queue::container_type (STL/CLR)](#container_type)|基になるコンテナーの型。|
|[priority_queue::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[priority_queue::generic_container (STL/CLR)](#generic_container)|コンテナーアダプターのジェネリックインターフェイスの型。|
|[priority_queue::generic_value (STL/CLR)](#generic_value)|コンテナーアダプターのジェネリックインターフェイスの要素の型。|
|[priority_queue::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[priority_queue::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[priority_queue::value_compare (STL/CLR)](#value_compare)|2つの要素の順序付けデリゲート。|
|[priority_queue::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[priority_queue::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[priority_queue::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[priority_queue::get_container (STL/CLR)](#get_container)|基になるコンテナーにアクセスします。|
|[priority_queue::pop (STL/CLR)](#pop)|優先順位の高い要素を削除します。|
|[priority_queue::priority_queue (STL/CLR)](#priority_queue)|コンテナー オブジェクトを構築します。|
|[priority_queue::push (STL/CLR)](#push)|新しい要素を追加します。|
|[priority_queue::size (STL/CLR)](#size)|要素の数をカウントします。|
|[priority_queue::top (STL/CLR)](#top)|最も優先順位の高い要素にアクセスします。|
|[priority_queue::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|
|[priority_queue::value_comp (STL/CLR)](#value_comp)|2 つの要素のための順序付けデリゲートをコピーします。|

|プロパティ|Description|
|--------------|-----------------|
|[priority_queue::top_item (STL/CLR)](#top_item)|最も優先順位の高い要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[priority_queue::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|I優先キュー\<Value, Container>|汎用コンテナーアダプターを維持します。|

## <a name="remarks"></a>解説

オブジェクトは、 `Container` 要素を格納し、必要に応じて拡張する、基になるコンテナー (型) によって制御されるシーケンスのストレージを割り当て、解放し `Value` ます。 シーケンスはヒープとして保持され、優先順位の高い要素 (最上位要素) はすぐにアクセス可能で、リムーバブルになります。 オブジェクトは、新しい要素をプッシュするためのアクセスを制限し、優先順位キューを実装して、優先順位の高い要素だけをポップします。

オブジェクトは、priority_queue:: value_compare 型の格納されたデリゲートオブジェクトを呼び出すことによって、制御するシーケンスを並べ替えます[(STL/CLR)](../dotnet/priority-queue-value-compare-stl-clr.md)。 Priority_queue を構築するときに、格納されているデリゲートオブジェクトを指定できます。デリゲートオブジェクトを指定しない場合、既定では比較が行われ `operator<(value_type, value_type)` ます。 この格納されているオブジェクトにアクセスするには、メンバー関数[priority_queue:: value_comp (STL/CLR)](../dotnet/priority-queue-value-comp-stl-clr.md)を呼び出し `()` ます。

このようなデリゲートオブジェクトは、 [priority_queue:: value_type 型の値 (STL/CLR)](../dotnet/priority-queue-value-type-stl-clr.md)に対して厳密弱順序を強制する必要があります。 つまり、任意の2つのキーについては、次のようになり `X` `Y` ます。

`value_comp()(X, Y)`すべての呼び出しで同じブール型の結果を返します。

`value_comp()(X, Y)`が true の場合、は `value_comp()(Y, X)` false である必要があります。

`value_comp()(X, Y)`が true の場合、 `X` はの前に並べられてい `Y` ます。

`!value_comp()(X, Y) && !value_comp()(Y, X)`が true の場合、 `X` と `Y` は等価の順序付けと呼ばれます。

`X`被制御シーケンスの前にある要素の場合 `Y` 、 `key_comp()(Y, X)` は false になります。 (既定のデリゲートオブジェクトの場合、キーの値が減少することはありません)。

最も優先順位の高い要素は、他の要素の前に順序付けされていない要素の1つです。

基になるコンテナーは要素をヒープとして保持するため、次のようになります。

コンテナーはランダムアクセス反復子をサポートする必要があります。

順序が同等の要素は、プッシュされた順序とは異なる順序でポップされることがあります。 (順序は安定していません)。

したがって、基になるコンテナーの候補として、 [deque (stl/clr)](../dotnet/deque-stl-clr.md)と[vector (stl/clr)](../dotnet/vector-stl-clr.md)があります。

## <a name="members"></a>メンバー

## <a name="priority_queueassign-stlclr"></a><a name="assign"></a>priority_queue:: assign (STL/CLR)

すべての要素を置換します。

### <a name="syntax"></a>構文

```cpp
void assign(priority_queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
挿入するコンテナーアダプター。

### <a name="remarks"></a>解説

このメンバー関数は、 `right.get_container()` 基になるコンテナーにを割り当てます。 キューの内容全体を変更するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign a repetition of values
    Mypriority_queue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="priority_queueconst_reference-stlclr"></a><a name="const_reference"></a>priority_queue:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mypriority_queue::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="priority_queuecontainer_type-stlclr"></a><a name="container_type"></a>priority_queue:: container_type (STL/CLR)

基になるコンテナーの型。

### <a name="syntax"></a>構文

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `Container` のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c" using container_type
    Mypriority_queue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queuedifference_type-stlclr"></a><a name="difference_type"></a>priority_queue::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute negative difference
    Mypriority_queue::difference_type diff = c1.size();
    c1.push(L'd');
    c1.push(L'e');
    diff -= c1.size();
    System::Console::WriteLine("pushing 2 = {0}", diff);

    // compute positive difference
    diff = c1.size();
    c1.pop();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("popping 3 = {0}", diff);
    return (0);
    }
```

```Output
c a b
pushing 2 = -2
popping 3 = 3
```

## <a name="priority_queueempty-stlclr"></a><a name="empty"></a>priority_queue:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[priority_queue:: size (STL/CLR)](../dotnet/priority-queue-size-stl-clr.md)に相当 `() == 0` します。 Priority_queue が空であるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());

    // clear the container and reinspect
    c1.pop();
    c1.pop();
    c1.pop();
    System::Console::WriteLine("size() = {0}", c1.size());
    System::Console::WriteLine("empty() = {0}", c1.empty());
    return (0);
    }
```

```Output
c a b
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="priority_queuegeneric_container-stlclr"></a><a name="generic_container"></a>priority_queue:: generic_container (STL/CLR)

コンテナーのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::IPriorityQueue<Value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナーアダプタークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct a generic container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify generic and display original
    gc1->push(L'd');
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify original and display generic
    c1.push(L'e');
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
d c b a
e d b a c
```

## <a name="priority_queuegeneric_value-stlclr"></a><a name="generic_value"></a>priority_queue:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、 `GValue` このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する型のオブジェクトを表します。 (はであるか、 `GValue` `value_type` `value_type^` `value_type` が ref 型である場合はです)。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // get interface to container
    Mypriority_queue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // display in priority order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mypriority_queue::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
c b a
```

## <a name="priority_queueget_container-stlclr"></a><a name="get_container"></a>priority_queue:: get_container (STL/CLR)

基になるコンテナーにアクセスします。

### <a name="syntax"></a>構文

```cpp
container_type get_container();
```

### <a name="remarks"></a>解説

このメンバー関数は、基になるコンテナーを返します。 コンテナーラッパーによって課される制限を回避するために使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queueoperator-stlclr"></a><a name="op_as"></a>priority_queue:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
priority_queue <Value, Container>% operator=(priority_queue <Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナーアダプター。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに*right*をコピーし、を返し **`*this`** ます。 このメソッドを使用して、被制御シーケンスを*右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // assign to a new container
    Mypriority_queue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
c a b
```

## <a name="priority_queuepop-stlclr"></a><a name="pop"></a>priority_queue::p op (STL/CLR)

最上位の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最優先順位の要素を削除します。この要素は、空にすることはできません。 これを使用して、キューを1つ前の要素で短くします。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // pop an element and redisplay
    c1.pop();
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
b a
```

## <a name="priority_queuepriority_queue-stlclr"></a><a name="priority_queue"></a>priority_queue::p riority_queue (STL/CLR)

コンテナーアダプターオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
priority_queue();
priority_queue(priority_queue<Value, Container> right);
priority_queue(priority_queue<Value, Container> right);
explicit priority_queue(value_compare^ pred);
priority_queue(value_compare^ pred, container_type% cont);
template<typename InIt>
    priority_queue(InIt first, InIt last);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred);
template<typename InIt>
    priority_queue(InIt first, InIt last,
        value_compare^ pred, container_type% cont);
```

#### <a name="parameters"></a>パラメーター

*連続*<br/>
コピーするコンテナー。

*first*<br/>
挿入する範囲の先頭。

*last*<br/>
挿入する範囲の末尾。

*pred*<br/>
被制御シーケンスの順序付け述語。

*そうです*<br/>
挿入するオブジェクトまたは範囲。

### <a name="remarks"></a>解説

コンストラクター:

`priority_queue();`

既定の順序述語を使用して、空のラップされたコンテナーを作成します。 このメソッドを使用して、既定の順序述語を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`priority_queue(priority_queue<Value, Container>% right);`

順序述語を使用して、のコピーであるラップされたコンテナーを作成し `right.get_container()` `right.value_comp()` ます。 このメソッドを使用して、キューオブジェクト*権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを、同じ順序述語を使用して指定します。

コンストラクター:

`priority_queue(priority_queue<Value, Container>^ right);`

順序述語を使用して、のコピーであるラップされたコンテナーを作成し `right->get_container()` `right->value_comp()` ます。 これを使用して、キューオブジェクトによって制御されるシーケンスのコピーである最初の被制御シーケンスを、同じ順序述語を使用して指定し `*right` ます。

コンストラクター:

`explicit priority_queue(value_compare^ pred);`

順序述語*pred*を使用して、空のラップされたコンテナーを作成します。 このメソッドを使用して、指定された順序述語を使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`priority_queue(value_compare^ pred, container_type cont);`

順序述語*pred*を使用して、空のラップされたコンテナーを作成します。次に、指定された順序述語を使用して、*既存のコンテナー*からの初期被制御シーケンスを指定するために、のすべての要素をプッシュします。

コンストラクター:

`template<typename InIt> priority_queue(InIt first, InIt last);`

既定の順序述語を使用して、空のラップされたコンテナーを作成し、シーケンス [,) をプッシュし `first` `last` ます。 指定された順序述語を使用して、指定された eqeuence の最初の被制御シーケンスを指定します。

コンストラクター:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred);`

順序述語*pred*を使用して、空のラップされたコンテナーを作成し、シーケンス [,) をプッシュし `first` `last` ます。 指定された順序述語を使用して、指定された seqeuence の最初の被制御シーケンスを指定します。

コンストラクター:

`template<typename InIt> priority_queue(InIt first, InIt last, value_compare^ pred, container_type% cont);`

順序述語*pred*を使用して、空のラップされたコンテナーを作成し、*継続*のすべての要素とシーケンス [,) をプッシュし `first` `last` ます。 このメソッドを使用して、指定された順序述語を使用して、既存のコンテナーと指定された seqeuence の最初の被制御シーケンスを指定します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/deque>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
typedef cliext::deque<wchar_t> Mydeque;
int main()
    {
// construct an empty container
    Mypriority_queue c1;
    Mypriority_queue::container_type^ wc1 = c1.get_container();
    System::Console::WriteLine("size() = {0}", c1.size());

    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    System::Console::WriteLine("size() = {0}", c2.size());

    for each (wchar_t elem in wc1)
        c2.push(elem);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule by copying an underlying container
    Mypriority_queue c2x =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
   for each (wchar_t elem in c2x.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range
    Mypriority_queue c3(wc1->begin(), wc1->end());
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range and an ordering rule
    Mypriority_queue c4(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>());
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an iterator range, another container, and an ordering rule
    Mypriority_queue c5(wc1->begin(), wc1->end(),
        cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c5.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct from a generic container
    Mypriority_queue c6(c3);
    for each (wchar_t elem in c6.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct by copying another container
    Mypriority_queue c7(%c3);
    for each (wchar_t elem in c7.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // construct with an ordering rule, by copying an underlying container
    Mypriority_queue c8 =
        gcnew Mypriority_queue(cliext::greater<wchar_t>(), *wc1);
    for each (wchar_t elem in c8.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    return (0);
    }
```

```Output
size() = 0
c a b
size() = 0
a c b
a c b
c a b
a c b
a a b c c b
c a b
c a b
a c b
```

## <a name="priority_queuepush-stlclr"></a><a name="push"></a>priority_queue::p u (STL/CLR)

新しい要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスに値を持つ要素を挿入し、被制御シーケンスを順序付けして `val` ヒープの統制を維持します。 これを使用して、キューに別の要素を追加します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
```

## <a name="priority_queuereference-stlclr"></a><a name="reference"></a>priority_queue:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // modify top of priority_queue and redisplay
    Mypriority_queue::reference ref = c1.top();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
x a b
```

## <a name="priority_queuesize-stlclr"></a><a name="size"></a>priority_queue:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスにゼロ以外のサイズがあるかどうかについては、「 [priority_queue:: empty (STL/CLR)](../dotnet/priority-queue-empty-stl-clr.md)」を参照してください `()` 。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    System::Console::WriteLine("size() = {0} starting with 3", c1.size());

    // pop an item and reinspect
    c1.pop();
    System::Console::WriteLine("size() = {0} after popping", c1.size());

    // add two elements and reinspect
    c1.push(L'a');
    c1.push(L'b');
    System::Console::WriteLine("size() = {0} after adding 2", c1.size());
    return (0);
    }
```

```Output
c a b
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="priority_queuesize_type-stlclr"></a><a name="size_type"></a>priority_queue:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // compute positive difference
    Mypriority_queue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
c a b
size difference = 2
```

## <a name="priority_queueto_array-stlclr"></a><a name="to_array"></a>priority_queue:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // copy the container and modify it
    cli::array<wchar_t>^ a1 = c1.to_array();

    c1.push(L'd');
    for each (wchar_t elem in c1.get_container())
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
d c b a
c a b
```

## <a name="priority_queuetop-stlclr"></a><a name="top"></a>priority_queue:: top (STL/CLR)

最も優先順位の高い要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference top();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最上位 (優先順位の高い) 要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最も優先順位の高い要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_top.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top() = {0}", c1.top());

    // alter last item and reinspect
    c1.top() = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

## <a name="priority_queuetop_item-stlclr"></a><a name="top_item"></a>priority_queue:: top_item (STL/CLR)

最も優先順位の高い要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type back_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最上位 (優先順位の高い) 要素にアクセスします。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最も優先順位の高い要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_top_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

    // inspect last item
    System::Console::WriteLine("top_item = {0}", c1.top_item);

    // alter last item and reinspect
    c1.top_item = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c a b
top_item = c
x a b
```

## <a name="priority_queuevalue_comp-stlclr"></a><a name="value_comp"></a>priority_queue:: value_comp (STL/CLR)

2 つの要素のための順序付けデリゲートをコピーします。

### <a name="syntax"></a>構文

```cpp
value_compare^ value_comp();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの順序付けに使用される順序付けデリゲートを返します。 2 つの値を比較する場合にこれを使用します。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_value_comp.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="priority_queuevalue_compare-stlclr"></a><a name="value_compare"></a>priority_queue:: value_compare (STL/CLR)

2つの値の順序付けデリゲート。

### <a name="syntax"></a>構文

```cpp
binary_delegate<value_type, value_type, int> value_compare;
```

### <a name="remarks"></a>解説

この型は、最初の引数が2番目の引数の前に並べ替えられるかどうかを決定するデリゲートのシノニムです。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_value_compare.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    Mypriority_queue::value_compare^ vcomp = c1.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
    System::Console::WriteLine();

    // test a different ordering rule
    Mypriority_queue c2 = cliext::greater<wchar_t>();
    vcomp = c2.value_comp();

    System::Console::WriteLine("compare(L'a', L'a') = {0}",
        vcomp(L'a', L'a'));
    System::Console::WriteLine("compare(L'a', L'b') = {0}",
        vcomp(L'a', L'b'));
    System::Console::WriteLine("compare(L'b', L'a') = {0}",
        vcomp(L'b', L'a'));
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

## <a name="priority_queuevalue_type-stlclr"></a><a name="value_type"></a>priority_queue:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター*値*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_priority_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::priority_queue<wchar_t> Mypriority_queue;
int main()
    {
    Mypriority_queue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

    // display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mypriority_queue::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```
