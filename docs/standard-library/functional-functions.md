---
title: '&lt;functional&gt; 関数 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- functional/std::bind
- xfunctional/std::bind1st
- xfunctional/std::bind2nd
- xfunctional/std::bit_and
- xfunctional/std::bit_not
- xfunctional/std::bit_or
- xfunctional/std::bit_xor
- functional/std::cref
- type_traits/std::cref
- xfunctional/std::mem_fn
- xfunctional/std::mem_fun_ref
- xfunctional/std::not1
- xfunctional/std::not2
- xfunctional/std::ptr_fun
- functional/std::ref
- functional/std::swap
dev_langs:
- C++
helpviewer_keywords:
- std::bind [C++]
- std::bind1st
- std::bind2nd
- std::bit_and [C++]
- std::bit_not [C++]
- std::bit_or [C++]
- std::bit_xor [C++]
- std::cref [C++]
ms.assetid: c34d0b45-50a7-447a-9368-2210d06339a4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5c93f32a7684d32cba0d2822571bd138f9206f46
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44107414"
---
# <a name="ltfunctionalgt-functions"></a>&lt;functional&gt; 関数

||||
|-|-|-|
|[bind](#bind)|[bind1st](#bind1st)|[bind2nd](#bind2nd)|
|[bit_and](#bit_and)|[bit_not](#bit_not)|[bit_or](#bit_or)|
|[bit_xor](#bit_xor)|[cref](#cref)|[mem_fn](#mem_fn)|
|[mem_fun](#mem_fun)|[mem_fun_ref](#mem_fun_ref)|[not1](#not1)|
|[not2](#not2)|[ptr_fun](#ptr_fun)|[ref](#ref)|
|[swap](#swap)|

## <a name="bind"></a>  bind

呼び出し可能オブジェクトに引数をバインドします。

```cpp
template <class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);

template <class Ret, class Fty, class T1, class T2, ..., class TN>
unspecified bind(Fty fn, T1 t1, T2 t2, ..., TN tN);
```

### <a name="parameters"></a>パラメーター

*Fty*<br/>
呼び出すオブジェクトの型。

*TN*<br/>
N 番目の引数の型。

*fn*<br/>
呼び出すオブジェクト。

*TN*<br/>
N 番目の呼び出しの引数。

### <a name="remarks"></a>Remarks

種類 `Fty, T1, T2, ..., TN` はコピーで構築可能である必要があり、`INVOKE(fn, t1, ..., tN)` はいくつかの値の有効な式にする必要があります。`w1, w2, ..., wN`

1 つ目のテンプレート関数は、転送呼び出しラッパー `g` と弱い結果型を返します。 効果`g(u1, u2, ..., uM)`は`INVOKE(f, v1, v2, ..., vN, ` [result_of](../standard-library/result-of-class.md)`<Fty cv (V1, V2, ..., VN)>::type)`ここで、`cv`の cv 修飾子は、`g`値と、バインドされる引数の型`v1, v2, ..., vN`として決定されます以下で指定します。 引数を呼び出し可能なオブジェクトにバインドしてカスタマイズされた引数リストを使用する呼び出し可能なオブジェクトを作成するためにそれを使用します。

2 つ目のテンプレート関数は、転送呼び出しラッパー `g` と入れ子になった型 `result_type` を返します。これは `Ret` のシノニムです。 `g(u1, u2, ..., uM)` の効果は `INVOKE(f, v1, v2, ..., vN, Ret)` です。`cv` は、`g` の cv 修飾子であり、バインドされる引数 `v1, v2, ..., vN` の値と型は以下のように決定されます。 引数を呼び出し可能なオブジェクトにバインドしてカスタマイズされた引数リストと指定された戻り値の型を使用する呼び出し可能なオブジェクトを作成しするためにそれを使用します。

バインドされている引数 `v1, v2, ..., vN` の値およびそれらの対応する型 `V1, V2, ..., VN` は、次のように、`bind` の呼び出しの型 `Ti` の対応する引数 `ti`、および呼び出しラッパー `g` の cv 修飾子 `cv` に依存します。

`ti` が型 `reference_wrapper<T>` である場合、引数 `vi` は `ti.get()` であり、型 `Vi` は `T&` です。

場合の値`std::is_bind_expression<Ti>::value`は**true**引数`vi`は`ti(u1, u2, ..., uM)`とその型`Vi`は`result_of<Ti` `cv` `(U1&, U2&, ..., UN&>::type`;

`std::is_placeholder<Ti>::value` の値 `j` が 0 である場合、引数 `vi` は `uj` であり、型 `Vi` は `Uj&` です。

それ以外の場合、引数 `vi` は `ti` であり、型 `Vi` は `Ti` `cv` `&` です。

たとえば、関数 `f(int, int)` を指定した場合、式 `bind(f, _1, 0)` は、`cw(x)` が `f(x, 0)` を呼び出すように、転送呼び出しラッパー `cw` を返します。 式 `bind(f, 0, _1)` は、`cw(x)` が `f(0, x)` を呼び出すように、転送呼び出しラッパー `cw` を返します。

`bind` に対する呼び出しの引数の数に引数 `fn` を加えた数が、呼び出し可能オブジェクト `fn` に渡すことができる引数の数と等しくなっている必要があります。 したがって、`bind(cos, 1.0)` が正しく、`bind(cos)` と `bind(cos, _1, 0.0)` はどちらも正しくありません。

`bind` によって返される呼出ラッパーに対する関数呼び出し内の引数の数は、`bind` に対する呼び出し内のすべてのプレースホルダー引数の `is_placeholder<PH>::value` の最高の数値以上になっている必要があります。 したがって、`bind(cos, _2)(0.0, 1.0)` が正しく (`cos(1.0)` を返します)、`bind(cos, _2)(0.0)` は正しくありません。

### <a name="example"></a>例

```cpp
// std__functional__bind.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

void product(double x, double y)
{
    std::cout << x << "*" << y << " == " << x * y << std::endl;
}

int main()
{
    double arg[] = { 1, 2, 3 };

    std::for_each(&arg[0], arg + 3, square);
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], arg + 3, std::bind(square, _1));

    return (0);
}

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="bind1st"></a>  bind1st

指定した値に二項関数の 1 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。

```cpp
template <class Operation, class Type>
binder1st <Operation> bind1st (const Operation& func, const Type& left);
```

### <a name="parameters"></a>パラメーター

*func*<br/>
単項関数オブジェクトに変換する二項関数オブジェクト。

*left*<br/>
二項関数オブジェクトの最初の引数がバインドされている値。

### <a name="return-value"></a>戻り値

単項関数オブジェクト、値に二項関数オブジェクトの最初の引数をバインドに起因する*左*します。

### <a name="remarks"></a>Remarks

関数バインダーには関数アダプターの一種であり、関数オブジェクトを返すので特定の種類の関数合成で使用して、より複雑で強力な式を作成することができます。

場合*func*型のオブジェクトは、`Operation`と`c`が定数の場合、 `bind1st` ( `func`、 `c`) と同じですが、 [binder1st](../standard-library/binder1st-class.md)クラスのコンス トラクター`binder1st` <  `Operation`> ( `func`、 `c`) と方が便利です。

### <a name="example"></a>例

```cpp
// functional_bind1st.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan5: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 5);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( " ;
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind1st(less<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare: counting the number of integers > 5 in the vector
    // with a user defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan5());
    cout << "The number of elements in v1 greater than 5 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind2nd(less<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 5 is: 4.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bind2nd"></a>  bind2nd

指定した値に二項関数の 2 番目の引数をバインドして二項関数オブジェクトを単項関数オブジェクトに変換するアダプターを作成するヘルパー テンプレート関数。

```cpp
template <class Operation, class Type>
binder2nd <Operation> bind2nd(const Operation& func, const Type& right);
```

### <a name="parameters"></a>パラメーター

*func*<br/>
単項関数オブジェクトに変換する二項関数オブジェクト。

*right*<br/>
二項関数オブジェクトの 2 つ目の引数がバインドされている値。

### <a name="return-value"></a>戻り値

値に二項関数オブジェクトの 2 番目の引数をバインドに起因する単項関数オブジェクト*右*します。

### <a name="remarks"></a>Remarks

関数バインダーには関数アダプターの一種であり、関数オブジェクトを返すので特定の種類の関数合成で使用して、より複雑で強力な式を作成することができます。

場合*func*型のオブジェクトは、`Operation`と`c`が定数の場合、 `bind2nd` ( `func`、 `c` ) と同じですが、 [binder2nd](../standard-library/binder2nd-class.md)クラスのコンス トラクター**binder2nd\<操作 >** ( `func`、 `c` ) でより便利です。

### <a name="example"></a>例

```cpp
// functional_bind2nd.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

// Creation of a user-defined function object
// that inherits from the unary_function base class
class greaterthan15: unary_function<int, bool>
{
public:
    result_type operator()(argument_type i)
    {
        return (result_type)(i > 15);
    }
};

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 5; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    // Count the number of integers > 10 in the vector
    vector<int>::iterator::difference_type result1a;
    result1a = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1a << "." << endl;

    // Compare counting the number of integers > 15 in the vector
    // with a user-defined function object
    vector<int>::iterator::difference_type result1b;
    result1b = count_if(v1.begin(), v1.end(), greaterthan15());
    cout << "The number of elements in v1 greater than 15 is: "
         << result1b << "." << endl;

    // Count the number of integers < 10 in the vector
    vector<int>::iterator::difference_type result2;
    result2 = count_if(v1.begin(), v1.end(), bind1st(greater<int>(), 10));
    cout << "The number of elements in v1 less than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 )
The number of elements in v1 greater than 10 is: 3.
The number of elements in v1 greater than 15 is: 2.
The number of elements in v1 less than 10 is: 2.
```

## <a name="bit_and"></a>  bit_and

引数に対してビットごとの AND 演算 (二項 `operator&`) を実行する定義済みの関数オブジェクト。

```cpp
template <class Type = void>
struct bit_and : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator&
template <>
struct bit_and<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const  ->
        decltype(std::forward<T>(Left) & std::forward<U>(Right));
};
```

### <a name="parameters"></a>パラメーター

*型*、 *T*、 *U*をサポートする任意の型、`operator&`指定または推論された型のオペランドを受け取る。

*左*<br/>
ビットごとの AND 演算の左オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*T*します。

*右*<br/>
ビットごとの AND 演算の右オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*U*します。

### <a name="return-value"></a>戻り値

`Left & Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator&` によって返された型が含まれます。

### <a name="remarks"></a>Remarks

`bit_and` ファンクターは、基本データ型の整数型、または二項 `operator&` を実装しているユーザー定義型に制限されます。

## <a name="bit_not"></a>  bit_not

引数に対してビットごとの補数 (NOT) 演算 (単項 `operator~`) を実行する定義済みの関数オブジェクト。

```cpp
template <class Type = void>
struct bit_not : public unary_function<Type, Type>
{
    Type operator()(const Type& Right) const;
};

// specialized transparent functor for operator~
template <>
struct bit_not<void>
{
    template <class Type>
    auto operator()(Type&& Right) const  ->  decltype(~std::forward<Type>(Right));
};
```

### <a name="parameters"></a>パラメーター

*Type*<br/>
単項 `operator~` をサポートする型。

*右*<br/>
ビットごとの補数演算の右オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートに完全推論された型の左辺値または右辺値参照引数の転送を行います*型*します。

### <a name="return-value"></a>戻り値

`~ Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator~` によって返された型が含まれます。

### <a name="remarks"></a>Remarks

`bit_not` ファンクターは、基本データ型の整数型、または二項 `operator~` を実装しているユーザー定義型に制限されます。

## <a name="bit_or"></a>  bit_or

引数に対してビットごとの OR 演算 (`operator|`) を実行する定義済みの関数オブジェクト。

```cpp
template <class Type = void>
struct bit_or : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator|
template <>
struct bit_or<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        ->  decltype(std::forward<T>(Left) | std::forward<U>(Right));
};
```

### <a name="parameters"></a>パラメーター

*型*、 *T*、 *U*をサポートする任意の型、`operator|`指定または推論された型のオペランドを受け取る。

*左*<br/>
ビットごとの OR 演算の左オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*T*します。

*右*<br/>
ビットごとの OR 演算の右オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*U*します。

### <a name="return-value"></a>戻り値

`Left | Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator|` によって返された型が含まれます。

### <a name="remarks"></a>Remarks

`bit_or` ファンクターは、基本データ型の整数型、または `operator|` を実装しているユーザー定義型に制限されます。

## <a name="bit_xor"></a>  bit_xor

引数に対してビットごとの XOR 演算 (二項 `operator^`) を実行する定義済みの関数オブジェクト。

```cpp
template <class Type = void>
struct bit_xor : public binary_function<Type, Type, Type> {
    Type operator()(
    const Type& Left,
    const Type& Right) const;
};

// specialized transparent functor for operator^
template <>
struct bit_xor<void>
{
    template <class T, class U>
    auto operator()(T&& Left, U&& Right) const
        -> decltype(std::forward<T>(Left) ^ std::forward<U>(Right));
};
```

### <a name="parameters"></a>パラメーター

*型*、 *T*、 *U*をサポートする任意の型、`operator^`指定または推論された型のオペランドを受け取る。

*左*<br/>
ビットごとの XOR 演算の左オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*T*します。

*右*<br/>
ビットごとの XOR 演算の右オペランド。 特化されていないテンプレートは、型の左辺値参照引数を受け取る*型*します。 特殊化されたテンプレートはの完全転送を左辺値と右辺値参照引数の型を推論する*U*します。

### <a name="return-value"></a>戻り値

`Left ^ Right` の結果。 特殊化されたテンプレートは、結果の完全転送を行います。結果には `operator^` によって返された型が含まれます。

### <a name="remarks"></a>Remarks

`bit_xor` ファンクターは、基本データ型の整数型、または二項 `operator^` を実装しているユーザー定義型に制限されます。

## <a name="cref"></a>  cref

引数から const の `reference_wrapper` を構築します。

```cpp
template <class Ty>
reference_wrapper<const Ty> cref(const Ty& arg);

template <class Ty>
reference_wrapper<const Ty> cref(const reference_wrapper<Ty>& arg);
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
ラップする引数の型。

*arg*<br/>
ラップする引数。

### <a name="remarks"></a>Remarks

最初の関数は `reference_wrapper<const Ty>(arg.get())` を返します。 定数参照をラップするために使用します。 2 番目の関数は `reference_wrapper<const Ty>(arg)` を返します。 ラップされた参照を定数参照として再ラップするために使用します。

### <a name="example"></a>例

```cpp
// std__functional__cref.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    int i = 1;

    std::cout << "i = " << i << std::endl;
    std::cout << "cref(i) = " << std::cref(i) << std::endl;
    std::cout << "cref(neg)(i) = "
        << std::cref(&neg)(i) << std::endl;

    return (0);
    }

```

```Output
i = 1
cref(i) = 1
cref(neg)(i) = -1
```

## <a name="mem_fn"></a>  mem_fn

単純な呼び出しラッパーを生成します。

```cpp
template <class Ret, class Ty>
unspecified mem_fn(Ret Ty::*pm);
```

### <a name="parameters"></a>パラメーター

*ret*<br/>
ラップされた関数の戻り値の型。

*Ty*<br/>
メンバー関数ポインターの型。

### <a name="remarks"></a>Remarks

テンプレート関数は、式 `cw(t, a2, ..., aN)` が `INVOKE(pm, t, a2, ..., aN)` と等しくなるように、単純な呼び出しラッパー `cw` と弱い結果型を返します。 この関数では、例外がスローされません。

返された呼び出しラッパーは派生`std::unary_function<cv Ty*, Ret>`(そのため入れ子にされた型を定義する`result_type`のシノニムとして*Ret*と入れ子にされた型`argument_type`のシノニムとして`cv Ty*`) 場合にのみ、型*Ty* cv 修飾子を持つメンバー関数へのポインターは、`cv`する引数を受け取りません。

返された呼び出しラッパーは派生`std::binary_function<cv Ty*, T2, Ret>`(そのため入れ子にされた型を定義する`result_type`のシノニムとして*Ret*、入れ子にされた型`first argument_type`のシノニムとして`cv Ty*`、および入れ子にされた型`second argument_type`のシノニムとして`T2`) 場合にのみ、型*Ty* cv 修飾子を持つメンバー関数へのポインターは、`cv`型の 1 つの引数を受け取る`T2`します。

### <a name="example"></a>例

```cpp
// std__functional__mem_fn.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

class Funs
    {
public:
    void square(double x)
        {
        std::cout << x << "^2 == " << x * x << std::endl;
        }

    void product(double x, double y)
        {
        std::cout << x << "*" << y << " == " << x * y << std::endl;
        }
    };

int main()
    {
    Funs funs;

    std::mem_fn(&Funs::square)(funs, 3.0);
    std::mem_fn(&Funs::product)(funs, 3.0, 2.0);

    return (0);
    }

```

```Output
3^2 == 9
3*2 == 6
```

## <a name="mem_fun"></a>  mem_fun

ポインター引数による初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。

```cpp
template <class Result, class Type>
mem_fun_t<Result, Type> mem_fun (Result(Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_t<Result, Type> mem_fun(Result (Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_t<Result, Type, Arg> mem_fun(Result (Type::* pmem)(Arg) const);
```

### <a name="parameters"></a>パラメーター

*pmem*<br/>
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

### <a name="return-value"></a>戻り値

型 `mem_fun_t` または `mem_fun1_t` の **const** または **non_const** 関数オブジェクト。

### <a name="example"></a>例

```cpp
// functional_mem_fun.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class StoreVals
{
    int val;
public:
    StoreVals() { val = 0; }
    StoreVals(int j) { val = j; }

    bool display() { cout << val << " "; return true; }
    int squareval() { val *= val; return val; }
    int lessconst(int k) {val -= k; return val; }
};

int main( )
{
    vector<StoreVals *> v1;

    StoreVals sv1(5);
    v1.push_back(&sv1);
    StoreVals sv2(10);
    v1.push_back(&sv2);
    StoreVals sv3(15);
    v1.push_back(&sv3);
    StoreVals sv4(20);
    v1.push_back(&sv4);
    StoreVals sv5(25);
    v1.push_back(&sv5);

    cout << "The original values stored are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun calling member function through a pointer
    // square each value in the vector using squareval ()
    for_each(v1.begin(), v1.end(), mem_fun<int, StoreVals>(&StoreVals::squareval));
    cout << "The squared values are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;

    // Use of mem_fun1 calling member function through a pointer
    // subtract 5 from each value in the vector using lessconst ()
    for_each(v1.begin(), v1.end(),
        bind2nd (mem_fun1<int, StoreVals,int>(&StoreVals::lessconst), 5));
    cout << "The squared values less 5 are: " ;
    for_each(v1.begin(), v1.end(), mem_fun<bool, StoreVals>(&StoreVals::display));
    cout << endl;
}
```

## <a name="mem_fun_ref"></a>  mem_fun_ref

参照引数を使用して初期化を行うときに、メンバー関数の関数オブジェクト アダプターを作成するために使用されるヘルパー テンプレート関数。

```cpp
template <class Result, class Type>
mem_fun_ref_t<Result, Type> mem_fun_ref(Result (Type::* pmem)());

template <class Result, class Type, class Arg>
mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (Type::* pmem)(Arg));

template <class Result, class Type>
const_mem_fun_ref_t<Result, Type> mem_fun_ref(Result Type::* pmem)() const);

template <class Result, class Type, class Arg>
const_mem_fun1_ref_t<Result, Type, Arg> mem_fun_ref(Result (T::* pmem)(Arg) const);
```

### <a name="parameters"></a>パラメーター

*pmem*<br/>
関数オブジェクトに変換されるクラス `Type` のメンバー関数へのポインター。

### <a name="return-value"></a>戻り値

A **const**または`non_const`型の関数オブジェクト`mem_fun_ref_t`または`mem_fun1_ref_t`します。

### <a name="example"></a>例

```cpp
// functional_mem_fun_ref.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

class NumVals
   {
   int val;
   public:
   NumVals ( ) { val = 0; }
   NumVals ( int j ) { val = j; }

   bool display ( ) { cout << val << " "; return true; }
   bool isEven ( ) { return ( bool )  !( val %2 ); }
   bool isPrime( )
   {
      if (val < 2) { return true; }
      for (int i = 2; i <= val / i; ++i)
      {
         if (val % i == 0) { return false; }
      }
      return true;
   }
};

int main( )
{
   vector <NumVals> v1 ( 13 ), v2 ( 13 );
   vector <NumVals>::iterator v1_Iter, v2_Iter;
   int i, k;

   for ( i = 0; i < 13; i++ ) v1 [ i ] = NumVals ( i+1 );
   for ( k = 0; k < 13; k++ ) v2 [ k ] = NumVals ( k+1 );

   cout << "The original values stored in v1 are: " ;
   for_each( v1.begin( ), v1.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the primes in the vector using isPrime ( )
   v1_Iter = remove_if ( v1.begin( ),  v1.end( ),
      mem_fun_ref ( &NumVals::isPrime ) );
   cout << "With the primes removed, the remaining values in v1 are: " ;
   for_each( v1.begin( ), v1_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   cout << "The original values stored in v2 are: " ;
   for_each( v2.begin( ), v2.end( ),
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;

   // Use of mem_fun_ref calling member function through a reference
   // remove the even numbers in the vector v2 using isEven ( )
   v2_Iter = remove_if ( v2.begin( ),  v2.end( ),
      mem_fun_ref ( &NumVals::isEven ) );
   cout << "With the even numbers removed, the remaining values are: " ;
   for_each( v2.begin( ),  v2_Iter,
   mem_fun_ref ( &NumVals::display ) );
   cout << endl;
}
```

```Output
The original values stored in v1 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the primes removed, the remaining values in v1 are: 4 6 8 9 10 12
The original values stored in v2 are: 1 2 3 4 5 6 7 8 9 10 11 12 13
With the even numbers removed, the remaining values are: 1 3 5 7 9 11 13
```

## <a name="not1"></a>  not1

単項述語の補数を返します。

```cpp
template <class UnaryPredicate>
unary_negate<UnaryPredicate> not1(const UnaryPredicate& pred);
```

### <a name="parameters"></a>パラメーター

*Pred*<br/>
符号が反転される単項述語。

### <a name="return-value"></a>戻り値

変更される単項述語の否定である単項述語。

### <a name="remarks"></a>Remarks

`unary_negate` が単項述語 **Pred**( *x*) から構築される場合、**!Pred**( *x*) を返します。

### <a name="example"></a>例

```cpp
// functional_not1.cpp
// compile with: /EHsc
#include <vector>
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std;

int main()
{
    vector<int> v1;
    vector<int>::iterator Iter;

    int i;
    for (i = 0; i <= 7; i++)
    {
        v1.push_back(5 * i);
    }

    cout << "The vector v1 = ( ";
    for (Iter = v1.begin(); Iter != v1.end(); Iter++)
        cout << *Iter << " ";
    cout << ")" << endl;

    vector<int>::iterator::difference_type result1;
    // Count the elements greater than 10
    result1 = count_if(v1.begin(), v1.end(), bind2nd(greater<int>(), 10));
    cout << "The number of elements in v1 greater than 10 is: "
         << result1 << "." << endl;

    vector<int>::iterator::difference_type result2;
    // Use the negator to count the elements less than or equal to 10
    result2 = count_if(v1.begin(), v1.end(),
        not1(bind2nd(greater<int>(), 10)));

    cout << "The number of elements in v1 not greater than 10 is: "
         << result2 << "." << endl;
}
```

```Output
The vector v1 = ( 0 5 10 15 20 25 30 35 )
The number of elements in v1 greater than 10 is: 5.
The number of elements in v1 not greater than 10 is: 3.
```

## <a name="not2"></a>  not2

二項述語の補数を返します。

```cpp
template <class BinaryPredicate>
binary_negate<BinaryPredicate> not2(const BinaryPredicate& func);
```

### <a name="parameters"></a>パラメーター

*func*<br/>
符号が反転される二項述語。

### <a name="return-value"></a>戻り値

変更される二項述語の否定である二項述語。

### <a name="remarks"></a>Remarks

`binary_negate` が二項述語 **BinPred**( *x*, *y*) から構築される場合、! **BinPred**( *x*, *y*) を返します。

### <a name="example"></a>例

```cpp
// functional_not2.cpp
// compile with: /EHsc
#include <vector>
#include <algorithm>
#include <functional>
#include <cstdlib>
#include <iostream>

int main( )
{
   using namespace std;
   vector <int> v1;
   vector <int>::iterator Iter1;

   int i;
   v1.push_back( 6262 );
   v1.push_back( 6262 );
   for ( i = 0 ; i < 5 ; i++ )
   {
      v1.push_back( rand( ) );
   }

   cout << "Original vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in ascending order,
   // use default binary predicate less<int>( )
   sort( v1.begin( ), v1.end( ) );
   cout << "Sorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;

   // To sort in descending order,
   // use the binary_negate helper function not2
   sort( v1.begin( ), v1.end( ), not2(less<int>( ) ) );
   cout << "Resorted vector v1 = ( " ;
   for ( Iter1 = v1.begin( ) ; Iter1 != v1.end( ) ; Iter1++ )
      cout << *Iter1 << " ";
   cout << ")" << endl;
}
```

```Output
Original vector v1 = ( 6262 6262 41 18467 6334 26500 19169 )
Sorted vector v1 = ( 41 6262 6262 6334 18467 19169 26500 )
Resorted vector v1 = ( 26500 19169 18467 6334 6262 6262 41 )
```

## <a name="ptr_fun"></a>  ptr_fun

単項関数ポインターと二項関数ポインターをそれぞれ適応性のある単項関数および二項関数に変換するために使用されるヘルパー テンプレート関数。

```cpp
template <class Arg, class Result>
pointer_to_unary_function<Arg, Result, Result (*)(Arg)> ptr_fun(Result (*pfunc)(Arg));

template <class Arg1, class Arg2, class Result>
pointer_to_binary_function<Arg1, Arg2, Result, Result (*)(Arg1, Arg2)> ptr_fun(Result (*pfunc)(Arg1, Arg2));
```

### <a name="parameters"></a>パラメーター

*pfunc*<br/>
アダプター関数に変換される単項関数ポインターまたは二項関数ポインター。

### <a name="return-value"></a>戻り値

最初のテンプレート関数は、単項関数を返します[pointer_to_unary_function](../standard-library/pointer-to-unary-function-class.md) < `Arg`、**結果**> (\* `pfunc`)。

2 番目のテンプレート関数は、二項関数を返します[pointer_to_binary_function](../standard-library/pointer-to-binary-function-class.md) \< **Arg1**、 **Arg2**、**結果**> (\* `pfunc`)。

### <a name="remarks"></a>Remarks

関数ポインターは関数オブジェクトであり、パラメーターとして関数を想定する C++ 標準ライブラリの任意のアルゴリズムに渡される場合がありますが、適応性はありません。 単項関数ポインターをアダプターと共に使用する (値をバインドしたり否定子と共に使用するなど) には、このような適応を可能にする、入れ子にされた型と共に指定する必要があります。 `ptr_fun` ヘルパー関数による単項関数ポインターと二項関数ポインターの変換では、関数アダプターと共に単項関数ポインターおよび二項関数ポインターを使用できます。

### <a name="example"></a>例

[!code-cpp[functional_ptr_fun#1](../standard-library/codesnippet/CPP/functional-functions_1.cpp)]

## <a name="ref"></a>  ref

引数から `reference_wrapper` を構築します。

```cpp
template <class Ty>
reference_wrapper<Ty> ref(Ty& arg);

template <class Ty>
reference_wrapper<Ty> ref(reference_wrapper<Ty>& arg);
```

### <a name="return-value"></a>戻り値

`arg`への参照。具体的には、 `reference_wrapper<Ty>(arg)`。

### <a name="example"></a>例

次の例では、2 つの関数を定義します。1 つは文字列変数にバインドされます。もう 1 つは、 `ref`の呼び出しによって計算された文字列変数の参照にバインドされます。 変数の値が変わると、1 つ目の関数では元の値が使用され続けますが、2 つ目の関数では新しい値が使用されます。

```cpp
#include <algorithm>
#include <functional>
#include <iostream>
#include <iterator>
#include <ostream>
#include <string>
#include <vector>
using namespace std;
using namespace std;
using namespace std::placeholders;

bool shorter_than(const string& l, const string& r) {
    return l.size() < r.size();
}

int main() {
    vector<string> v_original;
    v_original.push_back("tiger");
    v_original.push_back("cat");
    v_original.push_back("lion");
    v_original.push_back("cougar");

    copy(v_original.begin(), v_original.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    string s("meow");

    function<bool (const string&)> f = bind(shorter_than, _1, s);
    function<bool (const string&)> f_ref = bind(shorter_than, _1, ref(s));

    vector<string> v;

    // Remove elements that are shorter than s ("meow")

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Now change the value of s.
    // f_ref, which is bound to ref(s), will use the
    // new value, while f is still bound to the old value.

    s = "kitty";

    // Remove elements that are shorter than "meow" (f is bound to old value of s)

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;

    // Remove elements that are shorter than "kitty" (f_ref is bound to ref(s))

    v = v_original;
    v.erase(remove_if(v.begin(), v.end(), f_ref), v.end());

    copy(v.begin(), v.end(), ostream_iterator<string>(cout, " "));
    cout << endl;
}
```

```Output
tiger cat lion cougar
tiger lion cougar
tiger lion cougar
tiger cougar
```

## <a name="swap"></a>  swap

2 つの `function` オブジェクトを交換します。

```cpp
template <class Fty>
void swap(function<Fty>& f1, function<Fty>& f2);
```

### <a name="parameters"></a>パラメーター

*Fty*<br/>
関数オブジェクトによって制御される型。

*F1*<br/>
最初の関数オブジェクト。

*F2*<br/>
2 番目の関数オブジェクト。

### <a name="remarks"></a>Remarks

`f1.swap(f2)` が返されます。

### <a name="example"></a>例

```cpp
// std__functional__swap.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val)
    {
    return (-val);
    }

int main()
    {
    std::function<int (int)> fn0(neg);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << "val == " << fn0(3) << std::endl;

    std::function<int (int)> fn1;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << std::endl;

    swap(fn0, fn1);
    std::cout << std::boolalpha << "empty == " << !fn0 << std::endl;
    std::cout << std::boolalpha << "empty == " << !fn1 << std::endl;
    std::cout << "val == " << fn1(3) << std::endl;

    return (0);
    }

```

```Output
empty == false
val == -3
empty == true

empty == true
empty == false
val == -3
```

## <a name="see-also"></a>関連項目

[\<functional>](../standard-library/functional.md)<br/>
