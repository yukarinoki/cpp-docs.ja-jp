---
title: stack (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- cliext::stack
- cliext::stack::assign
- cliext::stack::const_reference
- cliext::stack::container_type
- cliext::stack::difference_type
- cliext::stack::empty
- cliext::stack::generic_container
- cliext::stack::generic_value
- cliext::stack::get_container
- cliext::stack::operator=
- cliext::stack::pop
- cliext::stack::push
- cliext::stack::reference
- cliext::stack::size
- cliext::stack::size_type
- cliext::stack::stack
- cliext::stack::to_array
- cliext::stack::top
- cliext::stack::top_item
- cliext::stack::value_type
helpviewer_keywords:
- <stack> header [STL/CLR]
- <cliext/stack> header [STL/CLR]
- stack class [STL/CLR]
- operator!= member [STL/CLR]
- operator< member [STL/CLR]
- operator<= member [STL/CLR]
- operator== member [STL/CLR]
- operator> member [STL/CLR]
- operator>= member [STL/CLR]
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
- push member [STL/CLR]
- reference member [STL/CLR]
- size member [STL/CLR]
- size_type member [STL/CLR]
- stack member [STL/CLR]
- to_array member [STL/CLR]
- top member [STL/CLR]
- top_item member [STL/CLR]
- value_type member [STL/CLR]
ms.assetid: 6ee96b9f-8a33-4cf7-b7e0-6535c24bdefb
ms.openlocfilehash: 18c94df643371f7b645ac9658a51d133d53f3403
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208326"
---
# <a name="stack-stlclr"></a>stack (STL/CLR)

このテンプレートクラスは、後入れ先出しアクセスを持つ要素の可変長シーケンスを制御するオブジェクトを表します。 コンテナーアダプター `stack` を使用すると、基になるコンテナーをプッシュダウンスタックとして管理できます。

次の説明では、`GValue` は、後者が参照型である場合を除き、*値*と同じです。この場合、`Value^`します。 同様に、`GContainer` は*コンテナー*と同じですが、後者が参照型である場合は `Container^`ます。

## <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    ref class stack
        :   public
        System::ICloneable,
        Microsoft::VisualC::StlClr::IStack<GValue, GContainer>
    { ..... };
```

### <a name="parameters"></a>パラメーター

*Value*<br/>
被制御シーケンス内の要素の型。

*コンテナー*<br/>
基になるコンテナーの型。

## <a name="requirements"></a>必要条件

**ヘッダー:** \<cliext/stack >

**名前空間:** cliext

## <a name="declarations"></a>宣言

|型定義|説明|
|---------------------|-----------------|
|[stack::const_reference (STL/CLR)](#const_reference)|要素への定数参照の型です。|
|[stack::container_type (STL/CLR)](#container_type)|基になるコンテナーの型。|
|[stack::difference_type (STL/CLR)](#difference_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[stack::generic_container (STL/CLR)](#generic_container)|コンテナーアダプターのジェネリックインターフェイスの型。|
|[stack::generic_value (STL/CLR)](#generic_value)|コンテナーアダプターのジェネリックインターフェイスの要素の型。|
|[stack::reference (STL/CLR)](#reference)|要素への参照の型です。|
|[stack::size_type (STL/CLR)](#size_type)|2 つの要素間の距離を表す、符号付きの型です。|
|[stack::value_type (STL/CLR)](#value_type)|要素の型。|

|メンバー関数|説明|
|---------------------|-----------------|
|[stack::assign (STL/CLR)](#assign)|すべての要素を置換します。|
|[stack::empty (STL/CLR)](#empty)|要素が存在しないかどうかをテストします。|
|[stack::get_container (STL/CLR)](#get_container)|基になるコンテナーにアクセスします。|
|[stack::pop (STL/CLR)](#pop)|最後の要素を削除します。|
|[stack::push (STL/CLR)](#push)|新しい最後の要素を追加します。|
|[stack::size (STL/CLR)](#size)|要素の数をカウントします。|
|[stack::stack (STL/CLR)](#stack)|コンテナー オブジェクトを構築します。|
|[stack::top (STL/CLR)](#top)|最後の要素にアクセスします。|
|[stack::to_array (STL/CLR)](#to_array)|被制御シーケンスを新しい配列にコピーします。|

|プロパティ|説明|
|--------------|-----------------|
|[stack::top_item (STL/CLR)](#top_item)|最後の要素にアクセスします。|

|演算子|説明|
|--------------|-----------------|
|[stack::operator= (STL/CLR)](#op_as)|被制御シーケンスを置き換えます。|
|[operator!= (stack) (STL/CLR)](#op_neq)|`stack` オブジェクトが別の `stack` オブジェクトと等しくないかどうかを判断します。|
|[operator< (stack) (STL/CLR)](#op_lt)|`stack` オブジェクトが、別の `stack` オブジェクトより小さいかどうかを判断します。|
|[operator<= (stack) (STL/CLR)](#op_lteq)|`stack` オブジェクトが、別の `stack` オブジェクト以下かどうかを判断します。|
|[operator== (stack) (STL/CLR)](#op_eq)|`stack` オブジェクトが別の `stack` オブジェクトと等しいかどうかを判断します。|
|[operator> (stack) (STL/CLR)](#op_gt)|`stack` オブジェクトが、別の `stack` オブジェクトより大きいかどうかを判断します。|
|[operator>= (stack) (STL/CLR)](#op_gteq)|`stack` オブジェクトが、別の `stack` オブジェクト以上かどうかを判断します。|

## <a name="interfaces"></a>インターフェイス

|インターフェイス|説明|
|---------------|-----------------|
|<xref:System.ICloneable>|オブジェクトを複製します。|
|IStack\<値、コンテナー >|汎用コンテナーアダプターを維持します。|

## <a name="remarks"></a>解説

オブジェクトは、コンテナー型の基になるコンテナー ( *container*) によって制御されるシーケンスのストレージを割り当て、解放します。このコンテナーは、*値*要素を格納し、必要に応じて拡大します。 オブジェクトは、最後の要素だけをプッシュしてポップするアクセスを制限し、最後の先入れ先出しキュー (LIFO キューまたはスタックとも呼ばれます) を実装します。

## <a name="members"></a>メンバー

## <a name="stackassign-stlclr"></a><a name="assign"></a>stack:: assign (STL/CLR)

すべての要素を置換します。

### <a name="syntax"></a>構文

```cpp
void assign(stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
挿入するコンテナーアダプター。

### <a name="remarks"></a>解説

このメンバー関数は、基になるコンテナーに `right.get_container()` を割り当てます。 スタックの内容全体を変更するには、これを使用します。

### <a name="example"></a>例

```cpp
// cliext_stack_assign.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign a repetition of values
    Mystack c2;
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

## <a name="stackconst_reference-stlclr"></a><a name="const_reference"></a>stack:: const_reference (STL/CLR)

要素への定数参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% const_reference;
```

### <a name="remarks"></a>解説

この型は、要素への定数参照を表します。

### <a name="example"></a>例

```cpp
// cliext_stack_const_reference.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " c b a"
    for (; !c1.empty(); c1.pop())
        {   // get a const reference to an element
        Mystack::const_reference cref = c1.top();
        System::Console::Write("{0} ", cref);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="stackcontainer_type-stlclr"></a><a name="container_type"></a>stack:: container_type (STL/CLR)

基になるコンテナーの型。

### <a name="syntax"></a>構文

```cpp
typedef Container value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレート パラメーター *Container* のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_stack_container_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Mystack::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="stackdifference_type-stlclr"></a><a name="difference_type"></a>stack::d ifference_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int difference_type;
```

### <a name="remarks"></a>解説

この型は、要素の数が負の値になる可能性があることを示します。

### <a name="example"></a>例

```cpp
// cliext_stack_difference_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute negative difference
    Mystack::difference_type diff = c1.size();
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

## <a name="stackempty-stlclr"></a><a name="empty"></a>stack:: empty (STL/CLR)

要素が存在しないかどうかをテストします。

### <a name="syntax"></a>構文

```cpp
bool empty();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスが空の場合に true を返します。 これは[stack:: size (STL/CLR)](../dotnet/stack-size-stl-clr.md)`() == 0`に相当します。 スタックが空であるかどうかをテストするために使用します。

### <a name="example"></a>例

```cpp
// cliext_stack_empty.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

## <a name="stackgeneric_container-stlclr"></a><a name="generic_container"></a>stack:: generic_container (STL/CLR)

コンテナーアダプターのジェネリックインターフェイスの型。

### <a name="syntax"></a>構文

```cpp
typedef Microsoft::VisualC::StlClr::IStack<Value>
    generic_container;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナーアダプタークラスのジェネリックインターフェイスを表します。

### <a name="example"></a>例

```cpp
// cliext_stack_generic_container.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Mystack::generic_container^ gc1 = %c1;
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

## <a name="stackgeneric_value-stlclr"></a><a name="generic_value"></a>stack:: generic_value (STL/CLR)

コンテナーのジェネリックインターフェイスで使用する要素の型。

### <a name="syntax"></a>構文

```cpp
typedef GValue generic_value;
```

### <a name="remarks"></a>解説

この型は、このテンプレートコンテナークラスのジェネリックインターフェイスで使用する格納されている要素の値を記述する `GValue` 型のオブジェクトを表します。 (`GValue` は、`value_type` が ref 型である場合は `value_type` または `value_type^` です)。

### <a name="example"></a>例

```cpp
// cliext_stack_generic_value.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// get interface to container
    Mystack::generic_container^ gc1 = %c1;
    for each (wchar_t elem in gc1->get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// display in reverse using generic_value
    for (; !gc1->empty(); gc1->pop())
        {
        Mystack::generic_value elem = gc1->top();

        System::Console::Write("{0} ", elem);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
a b c
c b a
```

## <a name="stackget_container-stlclr"></a><a name="get_container"></a>stack:: get_container (STL/CLR)

基になるコンテナーにアクセスします。

### <a name="syntax"></a>構文

```cpp
container_type^ get_container();
```

### <a name="remarks"></a>解説

このメンバー関数は、基になるコンテナーのハンドルを返します。 コンテナーラッパーによって課される制限を回避するために使用します。

### <a name="example"></a>例

```cpp
// cliext_stack_get_container.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c" using container_type
    Mystack::container_type wc1 = c1.get_container();
    for each (wchar_t elem in wc1)
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
a b c
```

## <a name="stackoperator-stlclr"></a><a name="op_as"></a>stack:: operator = (STL/CLR)

被制御シーケンスを置き換えます。

### <a name="syntax"></a>構文

```cpp
stack <Value, Container>% operator=(stack <Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コピーするコンテナーアダプター。

### <a name="remarks"></a>解説

メンバー演算子は、オブジェクトに*right*をコピーし、`*this`を返します。 このメソッドを使用して、被制御シーケンスを*右側*の被制御シーケンスのコピーで置き換えます。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_as.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="stackpop-stlclr"></a><a name="pop"></a>stack::p op (STL/CLR)

最後の要素を削除します。

### <a name="syntax"></a>構文

```cpp
void pop();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素を削除します。この要素は空にすることはできません。 これを使用して、スタックを1要素ずつ短くします。

### <a name="example"></a>例

```cpp
// cliext_stack_pop.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b
```

## <a name="stackpush-stlclr"></a><a name="push"></a>stack::p u (STL/CLR)

新しい最後の要素を追加します。

### <a name="syntax"></a>構文

```cpp
void push(value_type val);
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの末尾に `val` 値を持つ要素を挿入します。 このメソッドを使用して、別の要素をスタックに追加します。

### <a name="example"></a>例

```cpp
// cliext_stack_push.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

## <a name="stackreference-stlclr"></a><a name="reference"></a>stack:: reference (STL/CLR)

要素への参照の型です。

### <a name="syntax"></a>構文

```cpp
typedef value_type% reference;
```

### <a name="remarks"></a>解説

この型は、要素への参照を表します。

### <a name="example"></a>例

```cpp
// cliext_stack_reference.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// modify top of stack and redisplay
    Mystack::reference ref = c1.top();
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

## <a name="stacksize-stlclr"></a><a name="size"></a>stack:: size (STL/CLR)

要素の数をカウントします。

### <a name="syntax"></a>構文

```cpp
size_type size();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの長さを返します。 このメソッドを使用して、被制御シーケンス内の現在の要素数を決定します。 シーケンスに0以外のサイズがあるかどうかについては、「 [stack:: empty (STL/CLR)](../dotnet/stack-empty-stl-clr.md)`()`」を参照してください。

### <a name="example"></a>例

```cpp
// cliext_stack_size.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

## <a name="stacksize_type-stlclr"></a><a name="size_type"></a>stack:: size_type (STL/CLR)

2つの要素間の符号付き距離の型。

### <a name="syntax"></a>構文

```cpp
typedef int size_type;
```

### <a name="remarks"></a>解説

この型は、負でない要素数を表します。

### <a name="example"></a>例

```cpp
// cliext_stack_size_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display initial contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// compute positive difference
    Mystack::size_type diff = c1.size();
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

## <a name="stackstack-stlclr"></a><a name="stack"></a>stack:: stack (STL/CLR)

コンテナーアダプターオブジェクトを構築します。

### <a name="syntax"></a>構文

```cpp
stack();
stack(stack<Value, Container>% right);
stack(stack<Value, Container>^ right);
explicit stack(container_type% wrapped);
```

#### <a name="parameters"></a>パラメーター

*right*<br/>
コピーするオブジェクト。

*回り*<br/>
使用するためにラップされたコンテナー。

### <a name="remarks"></a>解説

コンストラクター:

`stack();`

空のラップされたコンテナーを作成します。 このメソッドを使用して、空の初期被制御シーケンスを指定します。

コンストラクター:

`stack(stack<Value, Container>% right);`

`right.get_container()`のコピーである、ラップされたコンテナーを作成します。 このメソッドを使用して、スタックオブジェクト*権限*によって制御されるシーケンスのコピーである最初の被制御シーケンスを指定します。

コンストラクター:

`stack(stack<Value, Container>^ right);`

`right->get_container()`のコピーである、ラップされたコンテナーを作成します。 これを使用して、スタックオブジェクト `*right`によって制御されるシーケンスのコピーである、最初の被制御シーケンスを指定します。

コンストラクター:

`explicit stack(container_type% wrapped);`

ラップされたコンテナーとして*ラップ*された既存のコンテナーを使用します。 これを使用して、既存のコンテナーからスタックを構築します。

### <a name="example"></a>例

```cpp
// cliext_stack_construct.cpp
// compile with: /clr
#include <cliext/stack>
#include <cliext/vector>

typedef cliext::stack<wchar_t> Mystack;
typedef cliext::vector<wchar_t> Myvector;
typedef cliext::stack<wchar_t, Myvector> Mystack_vec;
int main()
    {
// construct an empty container
    Mystack c1;
    System::Console::WriteLine("size() = {0}", c1.size());

// construct from an underlying container
    Myvector v2(5, L'x');
    Mystack_vec c2(v2);
    for each (wchar_t elem in c2.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container
    Mystack_vec c3(c2);
    for each (wchar_t elem in c3.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// construct by copying another container through handle
    Mystack_vec c4(%c2);
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

## <a name="stackto_array-stlclr"></a><a name="to_array"></a>stack:: to_array (STL/CLR)

被制御シーケンスを新しい配列にコピーします。

### <a name="syntax"></a>構文

```cpp
cli::array<Value>^ to_array();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスを含む配列を返します。 このメソッドを使用して、被制御シーケンスのコピーを配列形式で取得します。

### <a name="example"></a>例

```cpp
// cliext_stack_to_array.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

## <a name="stacktop-stlclr"></a><a name="top"></a>stack:: top (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
reference top();
```

### <a name="remarks"></a>解説

このメンバー関数は、被制御シーケンスの最後の要素への参照を返します。この要素は、空にすることはできません。 この要素が存在することがわかっている場合は、最後の要素にアクセスするために使用します。

### <a name="example"></a>例

```cpp
// cliext_stack_top.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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

```Output
a b c
top() = c
a b x
```

## <a name="stacktop_item-stlclr"></a><a name="top_item"></a>stack:: top_item (STL/CLR)

最後の要素にアクセスします。

### <a name="syntax"></a>構文

```cpp
property value_type top_item;
```

### <a name="remarks"></a>解説

プロパティは、被制御シーケンスの最後の要素にアクセスします。この要素は、空にすることはできません。 このメソッドは、最後の要素が存在することがわかっている場合に、その要素の読み取りまたは書き込みに使用します。

### <a name="example"></a>例

```cpp
// cliext_stack_top_item.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
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
a b c
top_item = c
a b x
```

## <a name="stackvalue_type-stlclr"></a><a name="value_type"></a>stack:: value_type (STL/CLR)

要素の型。

### <a name="syntax"></a>構文

```cpp
typedef Value value_type;
```

### <a name="remarks"></a>解説

この型は、テンプレートパラメーター*値*のシノニムです。

### <a name="example"></a>例

```cpp
// cliext_stack_value_type.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display reversed contents " a b c" using value_type
    for (; !c1.empty(); c1.pop())
        {   // store element in value_type object
        Mystack::value_type val = c1.top();

        System::Console::Write("{0} ", val);
        }
    System::Console::WriteLine();
    return (0);
    }
```

```Output
c b a
```

## <a name="operator-stack-stlclr"></a><a name="op_neq"></a>operator! = (stack) (STL/CLR)

スタックが等しくないかどうかの比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator!=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(left == right)`を返します。 このメソッドを使用して、2つのスタックが要素別に比較されるときに、 *left*が*right*と同じ順序で並んでいないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_ne.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="operatorlt-stack-stlclr"></a><a name="op_lt"></a>operator&lt; (stack) (STL/CLR)

スタックは比較していません。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator<(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

Operator 関数は、`!(right[i] < left[i])` が `left[i] < right[i]`にも当てはまる `i` 最小の位置に対して true を返します。 それ以外の場合は `left->`[stack:: size (STL/CLR)](../dotnet/stack-size-stl-clr.md) `right->size()``() <` を返します。このメソッドを使用して、2つのスタックが要素別に比較されるときに、 *left*が*right*の前に並べられているかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_lt.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="operatorlt-stack-stlclr"></a><a name="op_lteq"></a>operator&lt;= (stack) (STL/CLR)

スタックが以下であるかどうかを比較します。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator<=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(right < left)`を返します。 このメソッドを使用して、2つのスタックが要素別に比較されたときに、 *right*の後に*left*が順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_le.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="operator-stack-stlclr"></a><a name="op_eq"></a>operator = = (stack) (STL/CLR)

スタック等比較。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator==(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は、 *left*と*right*で制御されるシーケンスの長さが同じで、`i`位置ごとに `right[i]``left[i] ==` 場合にのみ true を返します。 このメソッドを使用して、2つのスタックが要素によって比較されるときに、 *left*が*right*と同じ順序で並んでいるかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_eq.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="operatorgt-stack-stlclr"></a><a name="op_gt"></a>operator&gt; (stack) (STL/CLR)

スタックが比較を超えています。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator>(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

Operator 関数は、`left``<` `right` を返します。 このメソッドを使用して、2つのスタックが要素によって比較されたときに、 *right* *の後にあるかどう*かをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_gt.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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

## <a name="operatorgt-stack-stlclr"></a><a name="op_gteq"></a>operator&gt;= (stack) (STL/CLR)

スタックが以上比較します。

### <a name="syntax"></a>構文

```cpp
template<typename Value,
    typename Container>
    bool operator>=(stack<Value, Container>% left,
        stack<Value, Container>% right);
```

#### <a name="parameters"></a>パラメーター

*left*<br/>
比較する左のコンテナー。

*right*<br/>
比較する右のコンテナー。

### <a name="remarks"></a>解説

演算子関数は `!(left < right)`を返します。 このメソッドを使用して、2つのスタックが要素別に比較されるときに、 *left*が*right*の前に順序付けされていないかどうかをテストします。

### <a name="example"></a>例

```cpp
// cliext_stack_operator_ge.cpp
// compile with: /clr
#include <cliext/stack>

typedef cliext::stack<wchar_t> Mystack;
int main()
    {
    Mystack c1;
    c1.push(L'a');
    c1.push(L'b');
    c1.push(L'c');

// display contents " a b c"
    for each (wchar_t elem in c1.get_container())
        System::Console::Write("{0} ", elem);
    System::Console::WriteLine();

// assign to a new container
    Mystack c2;
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
