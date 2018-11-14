---
title: shared_ptr クラス
ms.date: 11/04/2016
f1_keywords:
- memory/std::shared_ptr
- memory/std::shared_ptr::element_type
- memory/std::shared_ptr::get
- memory/std::shared_ptr::owner_before
- memory/std::shared_ptr::reset
- memory/std::shared_ptr::swap
- memory/std::shared_ptr::unique
- memory/std::shared_ptr::use_count
- memory/std::shared_ptr::operator boolean-type
- memory/std::shared_ptr::operator*
- memory/std::shared_ptr::operator=
- memory/std::shared_ptr::operator->
helpviewer_keywords:
- std::shared_ptr [C++]
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
- std::shared_ptr [C++], element_type
- std::shared_ptr [C++], get
- std::shared_ptr [C++], owner_before
- std::shared_ptr [C++], reset
- std::shared_ptr [C++], swap
- std::shared_ptr [C++], unique
- std::shared_ptr [C++], use_count
ms.assetid: 1469fc51-c658-43f1-886c-f4530dd84860
ms.openlocfilehash: 791a18461b3a0ee8237dec47c87f9d441221141d
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51519361"
---
# <a name="sharedptr-class"></a>shared_ptr クラス

参照カウント スマート ポインターを、動的に割り当てられたオブジェクトにラップします。

## <a name="syntax"></a>構文

```cpp
template <class T>
class shared_ptr;
```

## <a name="remarks"></a>Remarks

shared_ptr クラスは、参照カウントを使ってリソースを管理するオブジェクトを表します。 `shared_ptr` オブジェクトは、所有しているリソースへのポインターまたは null ポインターを効率的に保持します。 複数の `shared_ptr` オブジェクトが 1 つのリソースを所有することもできます。その場合、特定のリソースを所有する最後の `shared_ptr` オブジェクトが破棄された時点で、リソースが解放されます。

`shared_ptr` は、再割り当てまたはリセットされるとリソースの所有を停止します。

テンプレートの引数 `T` は、特定のメンバー関数について注記がある場合を除き、不完全な型になる場合があります。

`shared_ptr<T>` オブジェクトを `G*` 型のリソース ポインターまたは `shared_ptr<G>` から構築する場合、ポインターの型 `G*` は `T*` に変換可能であることが必要です。 この条件が満たされていない場合、コードはコンパイルされません。 例えば:

```cpp
#include <memory>
using namespace std;

class F {};
class G : public F {};

shared_ptr<G> sp0(new G);   // okay, template parameter G and argument G*
shared_ptr<G> sp1(sp0);     // okay, template parameter G and argument shared_ptr<G>
shared_ptr<F> sp2(new G);   // okay, G* convertible to F*
shared_ptr<F> sp3(sp0);     // okay, template parameter F and argument shared_ptr<G>
shared_ptr<F> sp4(sp2);     // okay, template parameter F and argument shared_ptr<F>
shared_ptr<int> sp5(new G); // error, G* not convertible to int*
shared_ptr<int> sp6(sp2);   // error, template parameter int and argument shared_ptr<F>
```

`shared_ptr` オブジェクトがリソースを所有するためには、次のいずれかの条件を満たしている必要があります。

- そのリソースへのポインターを使って構築されている。

- そのリソースを所有する `shared_ptr` オブジェクトから構築されている。

- そのリソースを指し示す [weak_ptr クラス](../standard-library/weak-ptr-class.md) オブジェクトから構築されている。

- そのリソースの所有権が、[shared_ptr::operator=](#op_eq) またはメンバー関数 [shared_ptr::reset](#reset) の呼び出しのいずれかによって割り当てられている。

リソースを所有する `shared_ptr` オブジェクトは、コントロール ブロックを共有します。 コントロール ブロックは以下の情報を保持します。

- リソースを所有する `shared_ptr` オブジェクトの数。

- リソースを指す `weak_ptr` オブジェクトの数。

- リソースの削除子 (存在する場合)

- コントロール ブロックのカスタム アロケーター (存在する場合)

null ポインターを使用して初期化される `shared_ptr` オブジェクトにはコントロール ブロックが存在し、空ではありません。 `shared_ptr` オブジェクトがリソースを所有するのは、そのリソースが解放されるまでの間です。 `weak_ptr` オブジェクトがリソースを指しているのは、そのリソースが解放されるまでの間です。

リソースを所有する `shared_ptr` オブジェクトの数がゼロになると、リソースを削除するか、リソースのアドレスを削除子に渡すことによって、リソースが解放されます。どちらの方法で解放されるかは、最初にリソースの所有権が作成された方法によって決定されます。 リソースを所有する `shared_ptr` オブジェクトの数がゼロになり、そのリソースを指す `weak_ptr` オブジェクトの数がゼロになると、コントロール ブロックのカスタム アロケーターを使用して (存在する場合)、コントロール ブロックが解放されます。

空の `shared_ptr` オブジェクトは、リソースを一切所有せず、コントロール ブロックも持ちません。

削除子は、メンバー関数 `operator()` を持つ関数オブジェクトです。 この型はコピーによって構築可能であること、また、コピー コンストラクターおよびデストラクターによって例外がスローされないことが必要です。 削除子は、削除するオブジェクトを指定する 1 つのパラメーターを受け入れます。

一部の関数では、結果として生成される `shared_ptr<T>` または `weak_ptr<T>` オブジェクトのプロパティを定義する引数リストが使用されます。 その場合、引数リストは次のような方法で指定できます。

引数なし: 結果として生成されるオブジェクトは、空の `shared_ptr` オブジェクトまたは空の `weak_ptr` オブジェクトです。

`ptr` -- 管理対象リソースへの `Other*` 型のポインター。 `T` は完全な型である必要があります。 コントロール ブロックを割り当てることができないため関数が失敗した場合、`delete ptr` という式が評価されます。

`ptr, dtor`: 管理対象リソースに対する `Other*` 型のポインターおよびそのリソースの削除子です。 コントロール ブロックを割り当てることができなかったことが原因で関数が失敗した場合、`dtor(ptr)` が呼び出されます (明確に定義されていることが必要)。

`ptr, dtor, alloc` -- 管理対象リソース、そのリソースの削除子、および割り当てと解放を行う必要があるすべてのストレージを管理するためのアロケーターへの `Other*` 型のポインター。 コントロール ブロックを割り当てることができなかったことが原因で関数が失敗した場合、`dtor(ptr)` が呼び出されます (明確に定義されていることが必要)。

`sp`: 管理対象のリソースを所有する `shared_ptr<Other>` オブジェクトです。

`wp`: 管理対象のリソースを指し示す `weak_ptr<Other>` オブジェクトです。

`ap`: 管理対象のリソースへのポインターを保持する `auto_ptr<Other>` オブジェクトです。 関数が成功した場合は、`ap.release()` が呼び出されます。関数が失敗した場合は、`ap` は変更されません。

いずれの場合も、ポインターの型 `Other*` は `T*` に変換可能である必要があります。

## <a name="thread-safety"></a>スレッド セーフ

複数のスレッドが異なる `shared_ptr` オブジェクト (所有権を共有するコピーである場合も含めて) に対する読み取りと書き込みを同時に行うことができます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[shared_ptr](#shared_ptr)|`shared_ptr` を構築します。|
|[shared_ptr::~shared_ptr](#dtorshared_ptr)|`shared_ptr` を破棄します。|

### <a name="types"></a>種類

|型名|説明|
|-|-|
|[element_type](#element_type)|要素の型。|

### <a name="functions"></a>関数

|関数|説明|
|-|-|
|[get](#get)|所有されているリソースのアドレスを取得します。|
|[owner_before](#owner_before)|この `shared_ptr` が、指定されたポインターの前に順序付けされている (またはそれよりも少ない) 場合は true を返します。|
|[reset](#reset)|所有されたリソースを置き換えます。|
|[swap](#swap)|2 つの `shared_ptr` オブジェクトを交換します。|
|[unique](#unique)|所有されたリソースが一意であるかどうかをテストします。|
|[use_count](#use_count)|リソース所有者の数をカウントします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[shared_ptr::operator bool](#op_bool)|所有されたリソースが存在するかどうかをテストします。|
|[shared_ptr::operator*](#op_star)|指定された値を取得します。|
|[shared_ptr::operator=](#op_eq)|所有されたリソースを置き換えます。|
|[shared_ptr::operator-&gt;](#op_arrow)|指定された値へのポインターを取得します。|

## <a name="requirements"></a>必要条件

**ヘッダー:** \<memory>

**名前空間:** std

## <a name="element_type"></a>  shared_ptr::element_type

要素の型。

```cpp
typedef T element_type;
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `T` のシノニムです。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::shared_ptr<int>::element_type val = *sp0;

    std::cout << "*sp0 == " << val << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="get"></a>  shared_ptr::get

所有されているリソースのアドレスを取得します。

```cpp
T *get() const;
```

### <a name="remarks"></a>Remarks

メンバー関数は、所有されたリソースのアドレスを返します。 オブジェクトがリソースを所有していない場合は、0 を返します。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_get.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "sp0.get() == 0 == " << std::boolalpha
        << (sp0.get() == 0) << std::endl;
    std::cout << "*sp1.get() == " << *sp1.get() << std::endl;

    return (0);
}
```

```Output
sp0.get() == 0 == true
*sp1.get() == 5
```

## <a name="op_bool"></a>  shared_ptr::operator bool

所有されたリソースが存在するかどうかをテストします。

```cpp
explicit operator bool() const noexcept;
```

### <a name="remarks"></a>Remarks

演算子の値を返します**true**とき`get() != nullptr`それ以外の場合、 **false**。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_operator_bool.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));

    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;
    std::cout << "(bool)sp1 == " << std::boolalpha
        << (bool)sp1 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
(bool)sp1 == true
```

## <a name="op_star"></a>  shared_ptr::operator*

指定された値を取得します。

```cpp
T& operator*() const;
```

### <a name="remarks"></a>Remarks

間接演算子は `*get()` を返します。 つまり、格納されたポインターは、null にすることはできません。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_operator_st.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));

    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
```

## <a name="op_eq"></a>  shared_ptr::operator=

所有されたリソースを置き換えます。

```cpp
shared_ptr& operator=(const shared_ptr& sp);

template <class Other>
shared_ptr& operator=(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>& ap);

template <class Other>
shared_ptr& operator=(auto_ptr<Other>&& ap);

template <class Other, class Deletor>
shared_ptr& operator=(unique_ptr<Other, Deletor>&& ap);
```

### <a name="parameters"></a>パラメーター

*sp*<br/>
コピーする共有ポインター。

*アジア太平洋*<br/>
コピーする自動ポインター。

### <a name="remarks"></a>Remarks

すべての演算子は、現在 `*this` によって所有されているリソースの参照数をデクリメントし、オペランド シーケンスで指定されたリソースの所有権を `*this` に割り当てます。 参照数がゼロになる場合は、リソースが解放されます。 演算子が失敗した場合、`*this` は変更されません。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0;
    std::shared_ptr<int> sp1(new int(5));
    std::auto_ptr<int> ap(new int(10));

    sp0 = sp1;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    sp0 = ap;
    std::cout << "*sp0 == " << *sp0 << std::endl;

    return (0);
}
```

```Output
*sp0 == 5
*sp0 == 10
```

## <a name="op_arrow"></a>  shared_ptr::operator-&gt;

指定された値へのポインターを取得します。

```cpp
T * operator->() const;
```

### <a name="remarks"></a>Remarks

`sp` がクラス `shared_ptr<T>` のオブジェクトである場合に式 `sp->member` が `(sp.get())->member` と同様に動作するよう、選択演算子は `get()` を返します。 そのため、格納されているポインターを null にすることはできず、`T` はメンバー `member` を持つクラス、構造体、または共用体型にする必要があります。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_operator_ar.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

typedef std::pair<int, int> Mypair;
int main()
{
    std::shared_ptr<Mypair> sp0(new Mypair(1, 2));

    std::cout << "sp0->first == " << sp0->first << std::endl;
    std::cout << "sp0->second == " << sp0->second << std::endl;

    return (0);
}
```

```Output
sp0->first == 1
sp0->second == 2
```

## <a name="owner_before"></a>  shared_ptr::owner_before

この `shared_ptr` が、指定されたポインターの前に順序付けされている (またはそれよりも少ない) 場合は true を返します。

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>パラメーター

*ptr*<br/>
`shared_ptr` または `weak_ptr` への `lvalue` 参照。

### <a name="remarks"></a>Remarks

テンプレート メンバー関数は、場合に true を返します`*this`は`ordered before``ptr`します。

## <a name="reset"></a>  shared_ptr::reset

所有されたリソースを置き換えます。

```cpp
void reset();

template <class Other>
void reset(Other *ptr;);

template <class Other, class D>
void reset(Other *ptr, D dtor);

template <class Other, class D, class A>
void reset(Other *ptr, D dtor, A alloc);
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
引数ポインターによって制御される型。

*D*<br/>
削除子の型。

*ptr*<br/>
コピーするポインター。

*dtor*<br/>
コピーする削除子。

*A*<br/>
アロケーターの型。

*Alloc*<br/>
コピーするアロケーター。

### <a name="remarks"></a>Remarks

すべての演算子は、現在 `*this` によって所有されているリソースの参照数をデクリメントし、オペランド シーケンスで指定されたリソースの所有権を `*this` に割り当てます。 参照数がゼロになる場合は、リソースが解放されます。 演算子が失敗した場合、`*this` は変更されません。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp(new int(5));

    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset();
    std::cout << "(bool)sp == " << std::boolalpha
        << (bool)sp << std::endl;

    sp.reset(new int(10));
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    sp.reset(new int(15), deleter());
    std::cout << "*sp == " << std::boolalpha
        << *sp << std::endl;

    return (0);
}
```

```Output
*sp == 5
(bool)sp == false
*sp == 10
*sp == 15
```

## <a name="shared_ptr"></a>  shared_ptr::shared_ptr

`shared_ptr` を構築します。

```cpp
shared_ptr();

shared_ptr(nullptr_t);

shared_ptr(const shared_ptr& sp);

shared_ptr(shared_ptr&& sp);

template <class Other>
explicit shared_ptr(Other* ptr);

template <class Other, class D>
shared_ptr(Other* ptr, D dtor);

template <class D>
shared_ptr(nullptr_t ptr, D dtor);

template <class Other, class D, class A>
shared_ptr(Other* ptr, D dtor, A  alloc);

template <class D, class A>
shared_ptr(nullptr_t ptr, D dtor, A alloc);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp);

template <class Other>
shared_ptr(const weak_ptr<Other>& wp);

template <class &>
shared_ptr(std::auto_ptr<Other>& ap);

template <class &>
shared_ptr(std::auto_ptr<Other>&& ap);

template <class Other, class D>
shared_ptr(unique_ptr<Other, D>&& up);

template <class Other>
shared_ptr(const shared_ptr<Other>& sp, T* ptr);

template <class Other, class D>
shared_ptr(const unique_ptr<Other, D>& up) = delete;
```

### <a name="parameters"></a>パラメーター

*その他*<br/>
引数ポインターによって制御される型。

*ptr*<br/>
コピーするポインター。

*D*<br/>
削除子の型。

*A*<br/>
アロケーターの型。

*dtor*<br/>
削除子。

*ator*<br/>
アロケーター。

*sp*<br/>
コピーするスマート ポインター。

*wp*<br/>
ウィーク ポインター。

*アジア太平洋*<br/>
コピーする自動ポインター。

### <a name="remarks"></a>Remarks

それぞれのコンストラクターは、オペランド シーケンスで指定されたリソースを所有するオブジェクトを構築します。 コンストラクター `shared_ptr(const weak_ptr<Other>& wp)` は、`wp.expired()` の場合に型 [bad_weak_ptr クラス](../standard-library/bad-weak-ptr-class.md)の例外オブジェクトをスローします。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp0;
    std::cout << "(bool)sp0 == " << std::boolalpha
        << (bool)sp0 << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    std::shared_ptr<int> sp2(new int(10), deleter());
    std::cout << "*sp2 == " << *sp2 << std::endl;

    std::shared_ptr<int> sp3(sp2);
    std::cout << "*sp3 == " << *sp3 << std::endl;

    std::weak_ptr<int> wp(sp3);
    std::shared_ptr<int> sp4(wp);
    std::cout << "*sp4 == " << *sp4 << std::endl;

    std::auto_ptr<int> ap(new int(15));
    std::shared_ptr<int> sp5(ap);
    std::cout << "*sp5 == " << *sp5 << std::endl;

    return (0);
}
```

```Output
(bool)sp0 == false
*sp1 == 5
*sp2 == 10
*sp3 == 10
*sp4 == 10
*sp5 == 15
```

## <a name="dtorshared_ptr"></a>  shared_ptr::~shared_ptr

`shared_ptr` を破棄します。

```cpp
~shared_ptr();
```

### <a name="remarks"></a>Remarks

デストラクターは、現在 `*this` によって所有されるリソースの参照数をデクリメントします。 参照数がゼロになる場合は、リソースが解放されます。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_destroy.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << "use count == " << sp1.use_count() << std::endl;

    {
        std::shared_ptr<int> sp2(sp1);
        std::cout << "*sp2 == " << *sp2 << std::endl;
        std::cout << "use count == " << sp1.use_count() << std::endl;
    }

    // check use count after sp2 is destroyed
    std::cout << "use count == " << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
use count == 1
*sp2 == 5
use count == 2
use count == 1
```

## <a name="swap"></a>  shared_ptr::swap

2 つの `shared_ptr` オブジェクトを交換します。

```cpp
void swap(shared_ptr& sp);
```

### <a name="parameters"></a>パラメーター

*sp*<br/>
交換先の共有ポインター。

### <a name="remarks"></a>Remarks

メンバー関数は、最初に所有してリソースを残します`*this`によって所有される*sp*、およびリソースを最初に所有して*sp*によって所有される`*this`します。 この関数はこれら 2 つのリソースの参照数を変更せず、例外をスローしません。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::shared_ptr<int> sp2(new int(10));
    std::cout << "*sp1 == " << *sp1 << std::endl;

    sp1.swap(sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;

    swap(sp1, sp2);
    std::cout << "*sp1 == " << *sp1 << std::endl;
    std::cout << std::endl;

    std::weak_ptr<int> wp1(sp1);
    std::weak_ptr<int> wp2(sp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    wp1.swap(wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    swap(wp1, wp2);
    std::cout << "*wp1 == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*sp1 == 5
*sp1 == 10
*sp1 == 5

*wp1 == 5
*wp1 == 10
*wp1 == 5
```

## <a name="unique"></a>  shared_ptr::unique

所有されたリソースが一意であるかどうかをテストします。

```cpp
bool unique() const;
```

### <a name="remarks"></a>Remarks

メンバー関数を返します**true**が他にない場合`shared_ptr`オブジェクトによって所有されているリソースを所有して`*this`それ以外の場合、 **false**します。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_unique.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

struct deleter
{
    void operator()(int *p)
    {
        delete p;
    }
};

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.unique() == " << std::boolalpha
        << sp1.unique() << std::endl;

    return (0);
}
```

```Output
sp1.unique() == true
sp1.unique() == false
```

## <a name="use_count"></a>  shared_ptr::use_count

リソース所有者の数をカウントします。

```cpp
long use_count() const;
```

### <a name="remarks"></a>Remarks

メンバー関数は、`*this` が所有するリソースを所有する `shared_ptr` オブジェクトの数を返します。

### <a name="example"></a>例

```cpp
// std__memory__shared_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "sp1.use_count() == "
        << sp1.use_count() << std::endl;

    return (0);
}
```

```Output
sp1.use_count() == 1
sp1.use_count() == 2
```

## <a name="see-also"></a>関連項目

[weak_ptr クラス](../standard-library/weak-ptr-class.md)<br/>
[C++ 標準ライブラリ内のスレッド セーフ](../standard-library/thread-safety-in-the-cpp-standard-library.md)<br/>
