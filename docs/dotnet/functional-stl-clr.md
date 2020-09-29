---
title: functional (STL/CLR)
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- <cliext/functional>
- cliext::binary_delegate
- cliext::binary_delegate_noreturn
- cliext::binary_negate
- cliext::bind1st
- cliext::bind2nd
- cliext::binder1st
- cliext::binder2nd
- cliext::divides
- cliext::equal_to
- cliext::greater
- cliext::greater_equal
- cliext::less
- cliext::less_equal
- cliext::logical_and
- cliext::logical_not
- cliext::logical_or
- cliext::minus
- cliext::modulus
- cliext::multiplies
- cliext::negate
- cliext::not_equal_to
- cliext::not1
- cliext::not2
- cliext::plus
- cliext::unary_delegate
- cliext::unary_delegate_noreturn
- cliext::unary_negate
helpviewer_keywords:
- <functional> header [STL/CLR]
- <cliext/functional> header [STL/CLR]
- functional functions [STL/CLR]
- binary_delegate function [STL/CLR]
- binary_delegate_noreturn function [STL/CLR]
- binary_negate function [STL/CLR]
- bind1st function [STL/CLR]
- bind2nd function [STL/CLR]
- binder1st function [STL/CLR]
- binder2nd function [STL/CLR]
- divides function [STL/CLR]
- equal_to function [STL/CLR]
- greater function [STL/CLR]
- greater_equal function [STL/CLR]
- less function [STL/CLR]
- less_equal function [STL/CLR]
- logical_and function [STL/CLR]
- logical_not function [STL/CLR]
- logical_or function [STL/CLR]
- minus function [STL/CLR]
- modulus function [STL/CLR]
- multiplies function [STL/CLR]
- negate function [STL/CLR]
- not_equal_to function [STL/CLR]
- not1 function [STL/CLR]
- not2 function [STL/CLR]
- plus function [STL/CLR]
- unary_delegate function [STL/CLR]
- unary_delegate_noreturn function [STL/CLR]
- unary_negate function [STL/CLR]
ms.assetid: 88738b8c-5d37-4375-970e-a4442bf5efde
ms.openlocfilehash: 00d719df2fdba892d1d9362da2b2172bac9ca16f
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/29/2020
ms.locfileid: "91499707"
---
# <a name="functional-stlclr"></a>functional (STL/CLR)

`<cliext/functional>`多数のテンプレートクラスと関連するテンプレートデリゲートおよび関数を定義するには、STL/CLR ヘッダーを含めます。

## <a name="syntax"></a>構文

```
#include <functional>
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<cliext/functional>

**名前空間:** cliext

## <a name="declarations"></a>宣言

|代理人|説明|
|--------------|-----------------|
|[binary_delegate (STL/CLR)](#binary_delegate)|2つの引数を持つデリゲート。|
|[binary_delegate_noreturn (STL/CLR)](#binary_delegate_noreturn)|2つの引数を返すデリゲート **`void`** 。|
|[unary_delegate (STL/CLR)](#unary_delegate)|1つの引数を持つデリゲート。|
|[unary_delegate_noreturn (STL/CLR)](#unary_delegate_noreturn)|1つの引数を返すデリゲート **`void`** 。|

|クラス|説明|
|-----------|-----------------|
|[binary_negate (STL/CLR)](#binary_negate)|2つの引数を持つファンクタを反転するためのファンクタ。|
|[binder1st (STL/CLR)](#binder1st)|最初の引数を2つの引数のファンクタにバインドするためのファンクタ。|
|[binder2nd (STL/CLR)](#binder2nd)|2番目の引数を2つの引数のファンクタにバインドするためのファンクタ。|
|[divides (STL/CLR)](#divides)|ファンクタを分割します。|
|[equal_to (STL/CLR)](#equal_to)|等しい比較ファンクタ。|
|[greater (STL/CLR)](#greater)|より大きい比較ファンクタ。|
|[greater_equal (STL/CLR)](#greater_equal)|大きいまたは等しい比較ファンクタ。|
|[less (STL/CLR)](#less)|比較できないファンクタ。|
|[less_equal (STL/CLR)](#less_equal)|小または等しい比較ファンクタ。|
|[logical_and (STL/CLR)](#logical_and)|論理とファンクタ。|
|[logical_not (STL/CLR)](#logical_not)|論理上のファンクタではありません。|
|[logical_or (STL/CLR)](#logical_or)|論理またはファンクタ。|
|[minus (STL/CLR)](#minus)|ファンクタを減算します。|
|[modulus (STL/CLR)](#modulus)|剰余ファンクタ。|
|[multiplies (STL/CLR)](#multiplies)|ファンクタを乗算します。|
|[negate (STL/CLR)](#negate)|引数を否定するファンクタ。|
|[not_equal_to (STL/CLR)](#not_equal_to)|等しくない比較ファンクタ。|
|[plus (STL/CLR)](#plus)|ファンクタを追加します。|
|[unary_negate (STL/CLR)](#unary_negate)|1つの引数のファンクタを反転させるためのファンクタ。|

|機能|説明|
|--------------|-----------------|
|[bind1st (STL/CLR)](#bind1st)|引数とファンクタの binder1st を生成します。|
|[bind2nd (STL/CLR)](#bind2nd)|引数とファンクタの binder2nd を生成します。|
|[not1 (STL/CLR)](#not1)|ファンクタの unary_negate を生成します。|
|[not2 (STL/CLR)](#not2)|ファンクタの binary_negate を生成します。|

## <a name="members"></a>メンバー

## <a name="binary_delegate-stlclr"></a><a name="binary_delegate"></a> binary_delegate (STL/CLR)

このクラスは、2つの引数を持つデリゲートを記述します。 これを使用して、引数と戻り値の型に関してデリゲートを指定します。

### <a name="syntax"></a>構文

```cpp
generic<typename Arg1,
    typename Arg2,
    typename Result>
    delegate Result binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>パラメーター

*Arg1*<br/>
1番目の引数の型。

*引数*<br/>
2番目の引数の型。

*結果*<br/>
戻り値の型。

### <a name="remarks"></a>注釈

このデリゲートでは、2つの引数を持つ関数が記述されています。

次の点に注意してください。

`binary_delegate<int, int, int> Fun1;`

`binary_delegate<int, int, int> Fun2;`

との型は `Fun1` `Fun2` シノニムで、次のようになります。

`delegate int Fun1(int, int);`

`delegate int Fun2(int, int);`

これらの型は同じではありません。

### <a name="example"></a>例

```cpp
// cliext_binary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

bool key_compare(wchar_t left, wchar_t right)
    {
    return (left < right);
    }

typedef cliext::binary_delegate<wchar_t, wchar_t, bool> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

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

## <a name="binary_delegate_noreturn-stlclr"></a><a name="binary_delegate_noreturn"></a> binary_delegate_noreturn (STL/CLR)

このクラスは、を返す2つの引数を持つデリゲートを記述し **`void`** ます。 引数を使用してデリゲートを指定します。

### <a name="syntax"></a>構文

```cpp
generic<typename Arg1,
    typename Arg2>
    delegate void binary_delegate(Arg1, Arg2);
```

#### <a name="parameters"></a>パラメーター

*Arg1*<br/>
1番目の引数の型。

*引数*<br/>
2番目の引数の型。

### <a name="remarks"></a>注釈

このデリゲートは、を返す2つの引数を持つ関数を記述し **`void`** ます。

次の点に注意してください。

`binary_delegate_noreturn<int, int> Fun1;`

`binary_delegate_noreturn<int, int> Fun2;`

との型は `Fun1` `Fun2` シノニムで、次のようになります。

`delegate void Fun1(int, int);`

`delegate void Fun2(int, int);`

これらの型は同じではありません。

### <a name="example"></a>例

```cpp
// cliext_binary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void key_compare(wchar_t left, wchar_t right)
    {
    System::Console::WriteLine("compare({0}, {1}) = {2}",
        left, right, left < right);
    }

typedef cliext::binary_delegate_noreturn<wchar_t, wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ kcomp = gcnew Mydelegate(&key_compare);

    kcomp(L'a', L'a');
    kcomp(L'a', L'b');
    kcomp(L'b', L'a');
    System::Console::WriteLine();
    return (0);
    }
```

```Output
compare(a, a) = False
compare(a, b) = True
compare(b, a) = False
```

## <a name="binary_negate-stlclr"></a><a name="binary_negate"></a> binary_negate (STL/CLR)

このテンプレートクラスは、が呼び出されると、格納されている2つの引数のファンクタの論理 NOT を返す、ファンクタを記述します。 これを使用して、格納されているファンクタの観点から関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    ref class binary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    explicit binary_negate(Fun% functor);
    binary_negate(binary_negate<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Fun*<br/>
格納されているファンクタの種類。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|
|stored_function_type|ファンクタの型。|

|メンバー|説明|
|------------|-----------------|
|binary_negate|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^ ()|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、別の2つの引数を持つファンクタを格納する2つの引数のファンクタを記述します。 このメソッドは、メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、2つの引数を指定して呼び出された格納されたファンの論理 NOT が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_binary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="bind1st-stlclr"></a><a name="bind1st"></a> bind1st (STL/CLR)

`binder1st`引数とファンクタのを生成します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun,
    typename Arg>
    binder1st<Fun> bind1st(Fun% functor,
        Arg left);
```

#### <a name="template-parameters"></a>テンプレート パラメーター

*Arg*<br/>
引数の型。

*Fun*<br/>
ファンクタの型。

#### <a name="function-parameters"></a>関数のパラメーター

*クタ*<br/>
ラップするファンクタ。

*左側*<br/>
ラップする1番目の引数。

### <a name="remarks"></a>注釈

このテンプレート関数は、 [binder1st (STL/CLR)](#binder1st)を返し `<Fun>(functor, left)` ます。 2つの引数を持つファンクタと、2番目の引数を使用して呼び出す1つの引数のファンクタでその最初の引数をラップする便利な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_bind1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="bind2nd-stlclr"></a><a name="bind2nd"></a> bind2nd (STL/CLR)

`binder2nd`引数とファンクタのを生成します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun,
    typename Arg>
    binder2nd<Fun> bind2nd(Fun% functor,
        Arg right);
```

#### <a name="template-parameters"></a>テンプレート パラメーター

*Arg*<br/>
引数の型。

*Fun*<br/>
ファンクタの型。

#### <a name="function-parameters"></a>関数のパラメーター

*クタ*<br/>
ラップするファンクタ。

*そうです*<br/>
ラップする2番目の引数。

### <a name="remarks"></a>注釈

このテンプレート関数は、 [binder2nd (STL/CLR)](#binder2nd)を返し `<Fun>(functor, right)` ます。 これは、2つの引数を持つファンクタと2番目の引数を、1番目の引数を使用して呼び出す1つの引数のファンクタにラップするための便利な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_bind2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="binder1st-stlclr"></a><a name="binder1st"></a> binder1st (STL/CLR)

このテンプレートクラスは、1つの引数を持つファンクタを記述します。これは、呼び出されると、格納されている最初の引数と指定された2番目の引数と共に、格納されている2つの引数のファンクタ これを使用して、格納されているファンクタの観点から関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    ref class binder1st
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        second_argument_type, result_type>
        delegate_type;

    binder1st(Fun% functor, first_argument_type left);
    binder1st(binder1st<Arg>% right);

    result_type operator()(second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Fun*<br/>
格納されているファンクタの種類。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|
|stored_function_type|ファンクタの型。|

|メンバー|説明|
|------------|-----------------|
|binder1st|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^ ()|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタと1番目の引数を格納する1つの引数のファンクタを記述します。 このメソッドは、メンバー演算子を定義します `operator()` 。これにより、オブジェクトが関数として呼び出されると、格納されている最初の引数と指定した2番目の引数を使用して、格納されたファンを呼び出した結果が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_binder1st.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder1st<cliext::minus<int> > subfrom3(sub_op, 3);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        subfrom3);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind1st(sub_op, 3));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
-1 0
-1 0
```

## <a name="binder2nd-stlclr"></a><a name="binder2nd"></a> binder2nd (STL/CLR)

このテンプレートクラスは、1つの引数を持つファンクタを記述します。これは、呼び出されると、指定された最初の引数と、格納されている2番目の引数で呼び出される、格納されている2つの引数のファン これを使用して、格納されているファンクタの観点から関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    ref class binder2nd
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::first_argument_type first_argument_type;
    typedef typename Fun::second_argument_type second_argument_type;
    typedef typename Fun:result_type result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        first_argument_type, result_type>
        delegate_type;

    binder2nd(Fun% functor, second_argument_type left);
    binder2nd(binder2nd<Arg>% right);

    result_type operator()(first_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Fun*<br/>
格納されているファンクタの種類。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|
|stored_function_type|ファンクタの型。|

|メンバー|説明|
|------------|-----------------|
|binder2nd|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^ ()|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタと2番目の引数を格納する1つの引数のファンクタを記述します。 このメソッドは、メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、指定された最初の引数と格納された2番目の引数を使用して、格納されたファンを呼び出した結果が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_binder2nd.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::minus<int> sub_op;
    cliext::binder2nd<cliext::minus<int> > sub4(sub_op, 4);

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        sub4);
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        bind2nd(sub_op, 4));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
0 -1
0 -1
```

## <a name="divides-stlclr"></a><a name="divides"></a> 除算 (STL/CLR)

このテンプレートクラスは、が呼び出されると、2番目の引数で除算された最初の引数を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class divides
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    divides();
    divides(divides<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数と戻り値の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|divides|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^ ()|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義します `operator()` 。これにより、オブジェクトが関数として呼び出されたときに、最初の引数を2番目の引数で割った値が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_divides.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::divides<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 3
```

## <a name="equal_to-stlclr"></a><a name="equal_to"></a> equal_to (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数と等しい場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    equal_to();
    equal_to(equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|equal_to|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^ ()|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義します。これにより、 `operator()` オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数と等しい場合にのみ true が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="greater-stlclr"></a><a name="greater"></a> より大きい (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数より大きい場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class greater
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater();
    greater(greater<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|greater|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義して、 `operator()` オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数より大きい場合にのみ true を返します。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_greater.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
1 0
```

## <a name="greater_equal-stlclr"></a><a name="greater_equal"></a> greater_equal (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数以上の場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class greater_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    greater_equal();
    greater_equal(greater_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|greater_equal|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義して、 `operator()` オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数以上の場合にのみ true を返します。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_greater_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::greater_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
```

## <a name="less-stlclr"></a><a name="less"></a> less (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数より小さい場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class less
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less();
    less(less<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|less|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義して、 `operator()` オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数より小さい場合にのみ true を返します。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_less.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="less_equal-stlclr"></a><a name="less_equal"></a> less_equal (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数の値以下である場合にのみ true を返す、ファンクタを表します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class less_equal
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    less_equal();
    less_equal(less_equal<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|less_equal|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義します `operator()` 。これにより、オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数の値以下である場合にのみ、true が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_less_equal.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(3);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 3 3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::less_equal<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
3 3
0 1
```

## <a name="logical_and-stlclr"></a><a name="logical_and"></a> logical_and (STL/CLR)

このテンプレートクラスは、1つ目の引数と2番目のテストの両方が true の場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class logical_and
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_and();
    logical_and(logical_and<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|logical_and|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、最初の引数と2番目のテストの両方が true の場合にのみ true を返します。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_logical_and.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 1 0" and " 1 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_and<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
3 0
1 0
```

## <a name="logical_not-stlclr"></a><a name="logical_not"></a> logical_not (STL/CLR)

このテンプレートクラスは、その引数が false としてテストされている場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class logical_not
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    logical_not();
    logical_not(logical_not<Arg> %right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|argument_type|ファンクタ引数の型。|
|delegate_type|ジェネリックデリゲートの型。|
|result_type|ファンクタの結果の型。|

|メンバー|説明|
|------------|-----------------|
|logical_not|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、1つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、引数が false としてテストされた場合にのみ true が返されるようになります。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_logical_not.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::logical_not<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
0 1
```

## <a name="logical_or-stlclr"></a><a name="logical_or"></a> logical_or (STL/CLR)

このテンプレートクラスは、1つ目の引数または2番目のテストが true の場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class logical_or
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    logical_or();
    logical_or(logical_or<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|logical_or|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、最初の引数または2番目のテストが true の場合にのみ true が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_logical_or.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(2);
    c1.push_back(0);
    Myvector c2;
    c2.push_back(0);
    c2.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 2 0" and " 0 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::logical_or<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
2 0
0 0
1 0
```

## <a name="minus-stlclr"></a><a name="minus"></a> マイナス (STL/CLR)

このテンプレートクラスは、呼び出したときに、最初の引数から2番目の引数を減算したものを返す、ファンクタを表します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class minus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    minus();
    minus(minus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数と戻り値の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|minus|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、最初の引数から2番目の引数を減算した値が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_minus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::minus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
2 2
```

## <a name="modulus-stlclr"></a><a name="modulus"></a> 剰余 (STL/CLR)

このテンプレートクラスは、を呼び出すと2番目の引数の剰余を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class modulus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    modulus();
    modulus(modulus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数と戻り値の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|modulus|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、1番目の引数の剰余が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_modulus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(2);
    Myvector c2;
    c2.push_back(3);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 2" and " 3 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::modulus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 2
3 1
1 0
```

## <a name="multiplies-stlclr"></a><a name="multiplies"></a> 乗算 (STL/CLR)

このテンプレートクラスは、呼び出したときに、最初の引数の1秒の時刻を返す、ファンクタを表します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class multiplies
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    multiplies();
    multiplies(multiplies<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数と戻り値の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|multiplies|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、最初の引数の1回目の時間が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_multiplies.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::multiplies<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
8 3
```

## <a name="negate-stlclr"></a><a name="negate"></a> 否定 (STL/CLR)

このテンプレートクラスは、呼び出したときにその引数を否定したものを返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class negate
    { // wrap operator()
public:
    typedef Arg argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    negate();
    negate(negate<Arg>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|argument_type|ファンクタ引数の型。|
|delegate_type|ジェネリックデリゲートの型。|
|result_type|ファンクタの結果の型。|

|メンバー|説明|
|------------|-----------------|
|negate|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、1つの引数を持つファンクタを記述します。 メンバー演算子を定義し `operator()` ます。これにより、オブジェクトが関数として呼び出されたときに、その引数を否定した値が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(-3);
    Myvector c3(2, 0);

// display initial contents " 4 -3"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c3.begin(), cliext::negate<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 -3
-4 3
```

## <a name="not_equal_to-stlclr"></a><a name="not_equal_to"></a> not_equal_to (STL/CLR)

このテンプレートクラスは、最初の引数が2番目の引数と等しくない場合にのみ true を返す、ファンクタを記述します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class not_equal_to
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    not_equal_to();
    not_equal_to(not_equal_to<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|not_equal_to|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義します。これにより、 `operator()` オブジェクトが関数として呼び出されたときに、最初の引数が2番目の引数と等しくない場合にのみ、true が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_not_equal_to.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not_equal_to<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
0 1
```

## <a name="not1-stlclr"></a><a name="not1"></a> not1 (STL/CLR)

`unary_negate`ファンクタのを生成します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    unary_negate<Fun> not1(Fun% functor);
```

#### <a name="template-parameters"></a>テンプレート パラメーター

*Fun*<br/>
ファンクタの型。

#### <a name="function-parameters"></a>関数のパラメーター

*クタ*<br/>
ラップするファンクタ。

### <a name="remarks"></a>注釈

このテンプレート関数は、 [unary_negate (STL/CLR)](#unary_negate)を返し `<Fun>(functor)` ます。 これは、論理 NOT を提供するファンクタで1つの引数のファンクタをラップするための便利な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_not1.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```

## <a name="not2-stlclr"></a><a name="not2"></a> not2 (STL/CLR)

`binary_negate`ファンクタのを生成します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    binary_negate<Fun> not2(Fun% functor);
```

#### <a name="template-parameters"></a>テンプレート パラメーター

*Fun*<br/>
ファンクタの型。

#### <a name="function-parameters"></a>関数のパラメーター

*クタ*<br/>
ラップするファンクタ。

### <a name="remarks"></a>注釈

このテンプレート関数は、 [binary_negate (STL/CLR)](#negate)を返し `<Fun>(functor)` ます。 論理 NOT を提供するファンクタで2つの引数を持つファンクタをラップする便利な方法として使用します。

### <a name="example"></a>例

```cpp
// cliext_not2.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(4);
    c2.push_back(4);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 4 4"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::less<int> less_op;

    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(),
        cliext::binary_negate<cliext::less<int> >(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::not2(less_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
4 4
1 0
1 0
```

## <a name="plus-stlclr"></a><a name="plus"></a> プラス (STL/CLR)

このテンプレートクラスは、呼び出したときに最初の引数に1を加算したものを返す、ファンクタを表します。 これを使用して、引数の型に関して関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Arg>
    ref class plus
    { // wrap operator()
public:
    typedef Arg first_argument_type;
    typedef Arg second_argument_type;
    typedef Arg result_type;
    typedef Microsoft::VisualC::StlClr::BinaryDelegate<
        first_argument_type, second_argument_type, result_type>
        delegate_type;

    plus();
    plus(plus<Arg>% right);

    result_type operator()(first_argument_type left,
        second_argument_type right);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数と戻り値の型。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|delegate_type|ジェネリックデリゲートの型。|
|first_argument_type|ファンクタの最初の引数の型。|
|result_type|ファンクタの結果の型。|
|second_argument_type|ファンクタの2番目の引数の型。|

|メンバー|説明|
|------------|-----------------|
|plus|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|演算子 delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、2つの引数を持つファンクタを記述します。 メンバー演算子を定義します `operator()` 。これにより、オブジェクトが関数として呼び出されるときに、最初の引数に1を加算した値が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_plus.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(3);
    Myvector c2;
    c2.push_back(2);
    c2.push_back(1);
    Myvector c3(2, 0);

// display initial contents " 4 3" and " 2 1"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

    for each (int elem in c2)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::transform(c1.begin(), c1.begin() + 2,
        c2.begin(), c3.begin(), cliext::plus<int>());
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 3
2 1
6 4
```

## <a name="unary_delegate-stlclr"></a><a name="unary_delegate"></a> unary_delegate (STL/CLR)

このクラスは、1つの引数を持つデリゲートを記述します。 これを使用して、引数と戻り値の型に関してデリゲートを指定します。

### <a name="syntax"></a>構文

```cpp
generic<typename Arg,
    typename Result>
    delegate Result unary_delegate(Arg);
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

*結果*<br/>
戻り値の型。

### <a name="remarks"></a>注釈

このデリゲートは、1つの引数を持つ関数を記述します。

次の点に注意してください。

`unary_delegare<int, int> Fun1;`

`unary_delegare<int, int> Fun2;`

との型は `Fun1` `Fun2` シノニムで、次のようになります。

`delegate int Fun1(int);`

`delegate int Fun2(int);`

これらの型は同じではありません。

### <a name="example"></a>例

```cpp
// cliext_unary_delegate.cpp
// compile with: /clr
#include <cliext/functional>

int hash_val(wchar_t val)
    {
    return ((val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate<wchar_t, int> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    System::Console::WriteLine("hash(L'a') = {0}", myhash(L'a'));
    System::Console::WriteLine("hash(L'b') = {0}", myhash(L'b'));
    return (0);
    }
```

```Output
hash(L'a') = 5
hash(L'b') = 22
```

## <a name="unary_delegate_noreturn-stlclr"></a><a name="unary_delegate_noreturn"></a> unary_delegate_noreturn (STL/CLR)

このクラスは、を返す1つの引数を持つデリゲートを記述し **`void`** ます。 これを使用して、引数の型に関してデリゲートを指定します。

### <a name="syntax"></a>構文

```cpp
generic<typename Arg>
    delegate void unary_delegate_noreturn(Arg);
```

#### <a name="parameters"></a>パラメーター

*Arg*<br/>
引数の型。

### <a name="remarks"></a>注釈

この関数では、を返す1つの引数を持つデリゲートが記述されて **`void`** います。

次の点に注意してください。

`unary_delegare_noreturn<int> Fun1;`

`unary_delegare_noreturn<int> Fun2;`

との型は `Fun1` `Fun2` シノニムで、次のようになります。

`delegate void Fun1(int);`

`delegate void Fun2(int);`

これらの型は同じではありません。

### <a name="example"></a>例

```cpp
// cliext_unary_delegate_noreturn.cpp
// compile with: /clr
#include <cliext/functional>

void hash_val(wchar_t val)
    {
    System::Console::WriteLine("hash({0}) = {1}",
       val, (val * 17 + 31) % 67);
    }

typedef cliext::unary_delegate_noreturn<wchar_t> Mydelegate;
int main()
    {
    Mydelegate^ myhash = gcnew Mydelegate(&hash_val);

    myhash(L'a');
    myhash(L'b');
    return (0);
    }
```

```Output
hash(a) = 5
hash(b) = 22
```

## <a name="unary_negate-stlclr"></a><a name="unary_negate"></a> unary_negate (STL/CLR)

このテンプレートクラスは、が呼び出されると、格納されている1つの引数のファンクタの論理 NOT を返す、ファンクタを記述します。 これを使用して、格納されているファンクタの観点から関数オブジェクトを指定します。

### <a name="syntax"></a>構文

```cpp
template<typename Fun>
    ref class unary_negate
    { // wrap operator()
public:
    typedef Fun stored_function_type;
    typedef typename Fun::argument_type argument_type;
    typedef bool result_type;
    typedef Microsoft::VisualC::StlClr::UnaryDelegate<
        argument_type, result_type>
        delegate_type;

    unary_negate(Fun% functor);
    unary_negate(unary_negate<Fun>% right);

    result_type operator()(argument_type left);
    operator delegate_type^();
    };
```

#### <a name="parameters"></a>パラメーター

*Fun*<br/>
格納されているファンクタの種類。

### <a name="member-functions"></a>メンバー関数

|型の定義|説明|
|---------------------|-----------------|
|argument_type|ファンクタ引数の型。|
|delegate_type|ジェネリックデリゲートの型。|
|result_type|ファンクタの結果の型。|

|メンバー|説明|
|------------|-----------------|
|unary_negate|ファンクタを構築します。|

|演算子|説明|
|--------------|-----------------|
|演算子 ()|目的の関数を計算します。|
|delegate_type ^|ファンクタをデリゲートにキャストします。|

### <a name="remarks"></a>注釈

このテンプレートクラスは、1つの引数を持つ別のファンクタを格納する1つの引数を持つファンクタを記述します。 このメソッドは、メンバー演算子を定義します `operator()` 。これにより、オブジェクトが関数として呼び出されたときに、引数と共に呼び出された格納されたファンの論理 NOT が返されます。

また、型がで、適切に変換される関数引数としてオブジェクトを渡すこともでき `delegate_type^` ます。

### <a name="example"></a>例

```cpp
// cliext_unary_negate.cpp
// compile with: /clr
#include <cliext/algorithm>
#include <cliext/functional>
#include <cliext/vector>

typedef cliext::vector<int> Myvector;
int main()
    {
    Myvector c1;
    c1.push_back(4);
    c1.push_back(0);
    Myvector c3(2, 0);

// display initial contents " 4 0"
    for each (int elem in c1)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display
    cliext::logical_not<int> not_op;

    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::unary_negate<cliext::logical_not<int> >(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();

// transform and display with function
    cliext::transform(c1.begin(), c1.begin() + 2, c3.begin(),
        cliext::not1(not_op));
    for each (int elem in c3)
        System::Console::Write(" {0}", elem);
    System::Console::WriteLine();
    return (0);
    }
```

```Output
4 0
1 0
1 0
```
