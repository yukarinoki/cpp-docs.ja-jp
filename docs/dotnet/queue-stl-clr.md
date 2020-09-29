---
title: queue (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::queue
- cliext::queue::assign
- cliext::queue::back
- cliext::queue::back_item
- cliext::queue::const_reference
- cliext::queue::container_type
- cliext::queue::difference_type
- cliext::queue::empty
- cliext::queue::front
- cliext::queue::front_item
- cliext::queue::generic_container
- cliext::queue::generic_value
- cliext::queue::get_container
- cliext::queue::operator=
- cliext::queue::pop
- cliext::queue::push
- cliext::queue::queue
- cliext::queue::reference
- cliext::queue::size
- cliext::queue::size_type
- cliext::queue::to_array
- cliext::queue::value_type
helpviewer_keywords:
- <queue> header [STL/CLR]
- queue class [STL/CLR]
- <cliext/queue> header [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
- assign member [STL/CLR]
- back member [STL/CLR]
- back_item member [STL/CLR]
- const_reference member [STL/CLR]
- container_type member [STL/CLR]
- difference_type member [STL/CLR]
- empty member [STL/CLR]
- front member [STL/CLR]
- front_item member [STL/CLR]
- generic_container member [STL/CLR]
- generic_value member [STL/CLR]
- get_container member [STL/CLR]
- operator= member [STL/CLR]
- pop member [STL/CLR]
- push member [STL/CLR]
- queue member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- to_array member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 9ea7dec3-ea98-48ff-87d0-a5afc924aaf2
ms.openlocfilehash: 2d5c1d30704838cdb69516d68d328c90a094a08e
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91502387"
---
# <a name="queue-stlclr"></a>queue (STL/CLR)

このテンプレートクラスは、先入れ先出しアクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナーアダプターは、 `queue` 基になるコンテナーをキューとして管理するために使用します。

次の説明で、 `GValue` は、後者が参照型である場合を除き、 *値* と同じです。この場合、は `Value^` です。 同様に、 `GContainer` は、後者が参照型である場合を除き、 *コンテナー* と同じです。この場合、は `Container^` です。

## <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    ref class queue
        :   public
        System::ICloneable,
        Microsoft::VisualC::StlClr::IQueue<GValue, GContainer>
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
|[queue::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[queue::container_type (STL/CLR)](#container_type)|基になるコンテナーの型。|
|[queue::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[queue::generic_container (STL/CLR)](#generic_container)|コンテナーアダプターのジェネリックインターフェイスの型。|
|[queue::generic_value (STL/CLR)](#generic_value)|コンテナーアダプターのジェネリックインターフェイスの要素の型。|
|[queue::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[queue::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[queue::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[queue::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[queue::back (STL/CLR)](#back)|最後の要素にアクセスします。|
|[queue::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[queue::front (STL/CLR)](#front)|最初の要素にアクセスします。|
|[queue::get_container (STL/CLR)](#get_container)|基になるコンテナーにアクセスします。|
|[queue::pop (STL/CLR)](#pop)|最初の要素を削除します。|
|[queue::push (STL/CLR)](#push)|新しい最後の要素を追加します。|
|[queue::queue (STL/CLR)](#queue)|コンテナー オブジェクトを構築します。|
|[queue::size (STL/CLR)](#size)|要素の数をカウントします。|
|[queue::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|

|プロパティ|説明|
|--------------|-----------------|
|[queue::back_item (STL/CLR)](#back_item)|最後の要素にアクセスします。|
|[queue::front_item (STL/CLR)](#front_item)|最初の要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[queue::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[operator! = (queue) (STL/CLR)](#op_neq)|オブジェクトが別のオブジェクトと等しくないかどうかを判断し `queue` `queue` ます。|
|[operator< (queue) (STL/CLR)](#op_lt)|`queue`オブジェクトが別のオブジェクトより小さいかどうかを判断し `queue` ます。|
|[operator<= (queue) (STL/CLR)](#op_lteq)|オブジェクトが別のオブジェクト以下かどうかを判断し `queue` `queue` ます。|
|[operator = = (queue) (STL/CLR)](#op_eq)|オブジェクトが別のオブジェクトと等しいかどうかを判断し `queue` `queue` ます。|
|[operator> (queue) (STL/CLR)](#op_gt)|`queue`オブジェクトが他のオブジェクトより大きいかどうかを判断し `queue` ます。|
|[operator>= (queue) (STL/CLR)](#op_gteq)|オブジェクトが別のオブジェクト以上かどうかを判断し `queue` `queue` ます。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|IQueue\<Value, Container>|汎用コンテナーアダプターを維持します。|

## <a name="remarks"></a>注釈

オブジェクトは、 `Container` 要素を格納し、必要に応じて拡張する、基になるコンテナー (型) によって制御されるシーケンスのストレージを割り当て、解放し `Value` ます。 オブジェクトは、最初の要素をプッシュして最後の要素をポップするだけにアクセスを制限し、先入れ先出しのキュー (FIFO キューとも呼ばれます) または単なるキューを実装します。

## <a name="members"></a>メンバー

## <a name="queueassign-stlclr"></a><a name="assign"></a> queue:: assign (STL/CLR)

すべての要素を置換します。

### <a name="syntax"></a>構文

```cpp
void assign(queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
挿入するコンテナーアダプター。

### <a name="remarks"></a>注釈

このメンバー関数は、 `right.get_container()` 基になるコンテナーにを割り当てます。 キューの内容全体を変更するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_assign.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign a repetition of values
    Myqueue c2;
    c2.assign(c1);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="queueback-stlclr"></a><a name="back"></a> queue:: back (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference back();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最後の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_back.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back() = {0}", c1.back());

// alter last item and reinspect
    c1.back() = L'x';
    for each (wchar_t elem in c1.get_container())
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

## <a name="queueback_item-stlclr"></a><a name="back_item"></a> queue:: back_item (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type back_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最後の要素にアクセスします。この要素は、空にすることはできません。 このメソッドは、最後の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_back_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("back_item = {0}", c1.back_item);

// alter last item and reinspect
    c1.back_item = L'x';
    for each (wchar_t elem in c1.get_container())
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

## <a name="queueconst_reference-stlclr"></a><a name="const_reference"></a> queue:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_queue_const_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Myqueue::const_reference cref = c1.front();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queuecontainer_type-stlclr"></a><a name="container_type"></a> queue:: container_type (STL/CLR)

基になるコンテナーの型。

### <a name="syntax"></a>構文

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター `Container` のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_queue_container_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Myqueue::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="queuedifference_type-stlclr"></a><a name="difference_type"></a> queue::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_queue_difference_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute negative difference
    Myqueue::difference_type diff = c1.size();
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
a b c
pushing 2 = -2
popping 3 = 3
```

## <a name="queueempty-stlclr"></a><a name="empty"></a> queue:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[queue:: size (STL/CLR)](#size)に相当 `() == 0` します。 このメソッドを使用して、キューが空かどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_empty.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
size() = 3
empty() = False
size() = 0
empty() = True
```

## <a name="queuefront-stlclr"></a><a name="front"></a> queue:: front (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference front();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最初の要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最初の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_front.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect first item
    System::Console::WriteLine("front() = {0}", c1.front());

// alter first item and reinspect
    c1.front() = L'x';
    for each (wchar_t elem in c1.get_container())
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

## <a name="queuefront_item-stlclr"></a><a name="front_item"></a> queue:: front_item (STL/CLR)

最初の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type front_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最初の要素にアクセスします。この要素は、空にすることはできません。 これは、最初の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_front_item.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// inspect last item
    System::Console::WriteLine("front_item = {0}", c1.front_item);

// alter last item and reinspect
    c1.front_item = L'x';
    for each (wchar_t elem in c1.get_container())
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

## <a name="queuegeneric_container-stlclr"></a><a name="generic_container"></a> queue:: generic_container (STL/CLR)

コンテナーアダプターのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::IQueue<Value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナーアダプタークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_queue_generic_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct a generic container
    Myqueue::generic_container^ gc1 = %c1;
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
a b c
a b c
a b c d
a b c d e
```

## <a name="queuegeneric_value-stlclr"></a><a name="generic_value"></a> queue:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、 `GValue` このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する型のオブジェクトを表します。 (はであるか、 `GValue` `value_type` `value_type^` `value_type` が ref 型である場合はです)。

### <a name="example"></a>例

```cpp
// cliext_queue_generic_value.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Myqueue::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display in order using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Myqueue::generic_value elem = gc1->front();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
a b c
```

## <a name="queueget_container-stlclr"></a><a name="get_container"></a> queue:: get_container (STL/CLR)

基になるコンテナーにアクセスします。

### <a name="syntax"></a>構文

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>解説

このメンバー関数は、基になるコンテナーを返します。 コンテナーラッパーによって課される制限を回避するために使用します。

### <a name="example"></a>例

```cpp
// cliext_queue_get_container.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
```

## <a name="queueoperator-stlclr"></a><a name="op_as"></a> queue:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
queue <Value, Container>% operator=(queue <Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするコンテナーアダプター。

### <a name="remarks"></a>注釈

メンバー演算子は、オブジェクトに *right* をコピーし、を返し **`*this`** ます。 このメソッドを使用して、被制御シーケンスを *右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_as.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2 = c1;
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
```

## <a name="queuepop-stlclr"></a><a name="pop"></a> queue::p op (STL/CLR)

最後の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素を削除します。この要素は空にすることはできません。 これを使用して、キューを1つ前の要素で短くします。

### <a name="example"></a>例

```cpp
// cliext_queue_pop.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
b c
```

## <a name="queuepush-stlclr"></a><a name="push"></a> queue::p u (STL/CLR)

新しい最後の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、キューの末尾に値を持つ要素を追加し `val` ます。 これを使用して、キューに要素を追加します。

### <a name="example"></a>例

```cpp
// cliext_queue_push.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
```

## <a name="queuequeue-stlclr"></a><a name="queue"></a> queue:: queue (STL/CLR)

コンテナーアダプターオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
queue();
queue(queue<Value, Container>% right);
queue(queue<Value, Container>^ right);
explicit queue(container_type% wrapped);
```

#### <a name="parameters"></a>パラメーター

*そうです*<br/>
コピーするオブジェクト。

*回り*<br/>
使用するためにラップされたコンテナー。

### <a name="remarks"></a>注釈

コンストラクター:

`queue();`

空のラップされたコンテナーを作成します。 このメソッドを使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`queue(queue<Value, Container>% right);`

のコピーである、ラップされたコンテナーを作成し `right.get_container()` ます。 このメソッドを使用して、キューオブジェクト *権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。

コンストラクター:

`queue(queue<Value, Container>^ right);`

のコピーである、ラップされたコンテナーを作成し `right->get_container()` ます。 これを使用して、キューオブジェクトによって制御されるシーケンスのコピーである最初の被制御シーケンスを指定し `*right` ます。

コンストラクター:

`explicit queue(container_type wrapped);`

ラップされたコンテナーとして *ラップ* された既存のコンテナーを使用します。 これを使用して、既存のコンテナーからキューを構築します。

### <a name="example"></a>例

```cpp
// cliext_queue_construct.cpp
// compile with: /clr
#include <cliext/queue>
#include <cliext/list>

typedef cliext::queue<wchar_t> Myqueue;
typedef cliext::list<wchar_t> Mylist;
typedef cliext::queue<wchar_t, Mylist> Myqueue_list;
int main()
    {
// construct an empty container
    Myqueue c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct from an underlying container
    Mylist v2(5, L'x');
    Myqueue_list c2(v2);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Myqueue_list c3(c2);
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container through handle
    Myqueue_list c4(%c2);
    for each (wchar_t elem in c4.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
size() = 0
x x x x x
x x x x x
x x x x x
```

## <a name="queuereference-stlclr"></a><a name="reference"></a> queue:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_queue_reference.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify back of queue and redisplay
    Myqueue::reference ref = c1.back();
    ref = L'x';
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b x
```

## <a name="queuesize-stlclr"></a><a name="size"></a> queue:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスのサイズが0以外であるかどうかについては、「 [queue:: empty (STL/CLR)](#empty)」を参照してください `()` 。

### <a name="example"></a>例

```cpp
// cliext_queue_size.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c
size() = 3 starting with 3
size() = 2 after popping
size() = 4 after adding 2
```

## <a name="queuesize_type-stlclr"></a><a name="size_type"></a> queue:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_queue_size_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Myqueue::size_type diff = c1.size();
    c1.pop();
    c1.pop();
    diff -= c1.size();
    System::Console::WriteLine("size difference = {0}", diff);
    return (0);
    }
```

```Output
a b c
size difference = 2
```

## <a name="queueto_array-stlclr"></a><a name="to_array"></a> queue:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_queue_to_array.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
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
a b c d
a b c
```

## <a name="queuevalue_type-stlclr"></a><a name="value_type"></a> queue:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター *値*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_queue_value_type.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Myqueue::value_type val = c1.front();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="operator-queue-stlclr"></a><a name="op_neq"></a> operator! = (queue) (STL/CLR)

キューが等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator!=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数はを返し `!(left == right)` ます。 このメソッドを使用して、2つのキューが要素別に比較されるときに、 *left* が *right* と同じ順序で並んでいないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_ne.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="operatorlt-queue-stlclr"></a><a name="op_lt"></a> 演算子 &lt; (queue) (STL/CLR)

キューの比較が少なくなっています。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator<(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数は、が true である場合にも true を返し `i` `!(right[i] < left[i])` `left[i] < right[i]` ます。 それ以外の場合は、 `left->` [queue:: size (STL/CLR)](#size)を返し `() <` `right->size()` ます。このメソッドを使用して、2つのキューが要素別に比較されるときに、 *left*が*right*の前に並べられているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_lt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="operatorlt-queue-stlclr"></a><a name="op_lteq"></a> operator &lt; = (queue) (STL/CLR)

キューの値が以下であるかどうかを比較します。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator<=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数はを返し `!(right < left)` ます。 このメソッドを使用して、2つのキューが要素別に比較されるときに、 *right*の後に*left*が順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_le.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="operator-queue-stlclr"></a><a name="op_eq"></a> operator = = (queue) (STL/CLR)

キューが等しいかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator==(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数は、 *左* と *右* で制御されるシーケンスの長さが同じで、各位置についてがである場合にのみ true を返し `i` `left[i] ==` `right[i]` ます。 このメソッドを使用して、2つのキューが要素別に比較されるときに、 *left* が *right* と同じ順序で並んでいるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_eq.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="operatorgt-queue-stlclr"></a><a name="op_gt"></a> 演算子 &gt; (queue) (STL/CLR)

キューが比較を超えています。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator>(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数はを返し `right` `<` `left` ます。 このメソッドを使用して、2つのキューが要素別に比較されたときに、 *right*の後にある*かどうか*をテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_gt.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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

## <a name="operatorgt-queue-stlclr"></a><a name="op_gteq"></a> operator &gt; = (queue) (STL/CLR)

キューが以上比較しています。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator>=(queue<Value, Container>% left,
        queue<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*左側*<br/>
比較する左のコンテナー。

*そうです*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>注釈

演算子関数はを返し `!(left < right)` ます。 このメソッドを使用して、2つのキューが要素別に比較されるときに、 *left* が *right* の前に順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_queue_operator_ge.cpp
// compile with: /clr
#include <cliext/queue>

typedef cliext::queue<wchar_t> Myqueue;
int main()
    {
    Myqueue c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Myqueue c2;
    c2.push(L'a');
    c2.push(L'b');
    c2.push(L'd');

// display contents " a b d"
    for each (wchar_t elem in c2.get_container())
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
