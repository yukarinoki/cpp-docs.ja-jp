---
title: weak_ptr クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- memory/std::weak_ptr
- memory/std::weak_ptr::element_type
- memory/std::weak_ptr::expired
- memory/std::weak_ptr::lock
- memory/std::weak_ptr::owner_before
- memory/std::weak_ptr::reset
- memory/std::weak_ptr::swap
- memory/std::weak_ptr::use_count
- memory/std::weak_ptr::operator=
dev_langs:
- C++
helpviewer_keywords:
- std::weak_ptr [C++]
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
- std::weak_ptr [C++], element_type
- std::weak_ptr [C++], expired
- std::weak_ptr [C++], lock
- std::weak_ptr [C++], owner_before
- std::weak_ptr [C++], reset
- std::weak_ptr [C++], swap
- std::weak_ptr [C++], use_count
ms.assetid: 2db4afb2-c7be-46fc-9c20-34ec2f8cc7c2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 03cd10d3efac16521cf826f3d9081ec533b9abec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="weakptr-class"></a>weak_ptr クラス

関連付けの弱いポインターをラップします。

## <a name="syntax"></a>構文

```cpp
template<class _Ty>
   class weak_ptr {
public:
   typedef Ty element_type;
   weak_ptr();
   weak_ptr(const weak_ptr&);
   template <class Other>
      weak_ptr(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr(const shared_ptr<Other>&);
   weak_ptr& operator=(const weak_ptr&);
   template <class Other>
      weak_ptr& operator=(const weak_ptr<Other>&);
   template <class Other>
      weak_ptr& operator=(shared_ptr<Other>&);
   void swap(weak_ptr&);
   void reset();
   long use_count() const;
   bool expired() const;
   shared_ptr<Ty> lock() const;
   };
```

### <a name="parameters"></a>パラメーター

`Ty` ウィーク ポインターによって制御される型。

## <a name="remarks"></a>コメント

このテンプレート クラスは、1 つ以上の [shared_ptr クラス](../standard-library/shared-ptr-class.md) オブジェクトによって管理されるリソースを指し示すオブジェクトを表します。 リソースを指し示す `weak_ptr` オブジェクトは、そのリソースの参照カウントに一切影響を与えません。 したがって、リソースを管理する最後の `shared_ptr` オブジェクトが破棄されると、仮にそのリソースを指し示す `weak_ptr` オブジェクトが存在していたとしても、そのリソースは解放されます。 これは、データ構造の循環を防ぐうえで不可欠です。

`weak_ptr` オブジェクトは、リソースを所有する `shared_ptr` オブジェクトから構築された場合や、リソースを指し示す `weak_ptr` オブジェクトから構築された場合、またはリソースが [operator=](#op_eq) を使って割り当てられた場合に、そのリソースを指し示します。 `weak_ptr` オブジェクトから、そのオブジェクトが指し示すリソースに直接アクセスすることはできません。 そのリソースを使用する必要があるコードは、メンバー関数 [lock](#lock) を呼び出すことによって作成された、そのリソースを所有する `shared_ptr` オブジェクトを介してそのリソースを使用します。 `weak_ptr` オブジェクトは、そのオブジェクトが指し示すリソースが解放されると、そのリソースを所有するすべての `shared_ptr` オブジェクトが破棄されるため、期限切れになります。 有効期限の切れた `weak_ptr` オブジェクトで `lock` を呼び出すと、空の shared_ptr オブジェクトが作成されます。

空の weak_ptr オブジェクトは、リソースを一切参照せず、コントロール ブロックも持ちません。 そのメンバー関数 `lock` は、空の shared_ptr オブジェクトを返します。

循環は、`shared_ptr` オブジェクトによって制御される複数のリソースで、相互に参照し合う `shared_ptr` オブジェクトが保持されているときに発生します。 たとえば、3 つの要素から成るリンク リストがあるとします。先頭のノード `N0` が 2 番目のノード `N1` を所有する `shared_ptr` オブジェクトを保持し、2 番目のノードが 3 番目のノード `N2` を所有する `shared_ptr` オブジェクトを保持し、次に、3 番目のノードが先頭のノード `N0` を所有する `shared_ptr` オブジェクトを保持しているとすると、ループが閉じた状態になり、このリストは循環リンク リストになります。 この状況では、どの参照カウントもゼロにならないので、循環内のノードは解放されません。 この循環を解消するためには、最後のノード `N2` が、`shared_ptr` オブジェクトではなく、`N0` を指し示す `weak_ptr` オブジェクトを保持する必要があります。 `weak_ptr` オブジェクトは `N0` を所有しないので、`N0` の参照カウントに影響しません。先頭ノードに対するプログラムの最後の参照が破棄された時点で、リスト内のノードも破棄されます。

## <a name="members"></a>メンバー

### <a name="constructors"></a>コンストラクター

|コンストラクター|説明|
|-|-|
|[weak_ptr](#weak_ptr)|`weak_ptr` を構築します。|

### <a name="methods"></a>メソッド

|||
|-|-|
|[element_type](#element_type)|要素の型。|
|[expired](#expired)|所有権の有効期限が切れているかどうかをテストします。|
|[lock](#lock)|リソースの排他的所有権を取得します。|
|[owner_before](#owner_before)|この `weak_ptr` が、指定されたポインターの前 (より小さい) に順序付けされている場合は `true` を返します。|
|[reset](#reset)|所有されたリソースを解放します。|
|[swap](#swap)|2 つの `weak_ptr` オブジェクトを交換します。|
|[use_count](#use_count)|指定された `shared_ptr` オブジェクトの数をカウントします。|

### <a name="operators"></a>演算子

|演算子|説明|
|-|-|
|[operator=](#op_eq)|所有されたリソースを置換します。|

## <a name="requirements"></a>要件

**ヘッダー:** \<memory>

**名前空間:** std

## <a name="element_type"></a>  element_type

要素の型。

```cpp
typedef Ty element_type;
```

### <a name="remarks"></a>コメント

この型は、テンプレート パラメーター `Ty` のシノニムです。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_element_type.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
    {
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::weak_ptr<int>::element_type val = *wp0.lock();

    std::cout << "*wp0.lock() == " << val << std::endl;

    return (0);
    }

```

```Output
*wp0.lock() == 5
```

## <a name="expired"></a>  expired

所有権の有効期限が切れているかどうかをテストします。

```cpp
bool expired() const;
```

### <a name="remarks"></a>コメント

メンバー関数は `*this` の期限が切れた場合に `true` を返し、それ以外の場合は `false` を返します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_expired.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}

```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="lock"></a>  lock

リソースの排他的所有権を取得します。

```cpp
shared_ptr<Ty> lock() const;
```

### <a name="remarks"></a>コメント

場合、メンバー関数は、空の shared_ptr オブジェクトを返します`*this`有効期限が切れた; を返しますそれ以外の場合、 [shared_ptr クラス](../standard-library/shared-ptr-class.md)\<Ty >、リソースを所有しているオブジェクト`*this`を指します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_lock.cpp
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
    std::weak_ptr<int> wp;

    {
        std::shared_ptr<int> sp(new int(10));
        wp = sp;
        std::cout << "wp.expired() == " << std::boolalpha
            << wp.expired() << std::endl;
        std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    }

    // check expired after sp is destroyed
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;
    std::cout << "(bool)wp.lock() == " << std::boolalpha
        << (bool)wp.lock() << std::endl;

    return (0);
}
```

```Output
wp.expired() == false
*wp.lock() == 10
wp.expired() == true
(bool)wp.lock() == false
```

## <a name="op_eq"></a>  operator=

所有されたリソースを置換します。

```cpp
weak_ptr& operator=(const weak_ptr& wp);

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

`Other` 引数の共有/ウィーク ポインターによって制御される型。

`wp` コピーするウィーク ポインター。

`sp` 共有ポインターにコピーします。

### <a name="remarks"></a>コメント

すべての演算子は、現在 `*this` によって指し示されているリソースを解放し、オペランド シーケンスで指定されたリソースの所有権を `*this` に割り当てます。 演算子が失敗した場合、`*this` は変更されません。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_operator_as.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp0(new int(5));
    std::weak_ptr<int> wp0(sp0);
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::shared_ptr<int> sp1(new int(10));
    wp0 = sp1;
    std::cout << "*wp0.lock() == " << *wp0.lock() << std::endl;

    std::weak_ptr<int> wp1;
    wp1 = wp0;
    std::cout << "*wp1.lock() == " << *wp1.lock() << std::endl;

    return (0);
}
```

```Output
*wp0.lock() == 5
*wp0.lock() == 10
*wp1.lock() == 10
```

## <a name="owner_before"></a>  owner_before

この `weak_ptr` が、指定されたポインターの前 (より小さい) に順序付けされている場合は `true` を返します。

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr);

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr);
```

### <a name="parameters"></a>パラメーター

`ptr` `lvalue`への参照、`shared_ptr`または`weak_ptr`です。

### <a name="remarks"></a>コメント

テンプレート メンバー関数を返します`true`場合`*this`は`ordered before``ptr`です。

## <a name="reset"></a>  reset

所有されたリソースを解放します。

```cpp
void reset();
```

### <a name="remarks"></a>コメント

このメンバー関数は `*this` によって指し示されるリソースを解放し、`*this` を空の weak_ptr オブジェクトに変換します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_reset.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp(new int(5));
    std::weak_ptr<int> wp(sp);
    std::cout << "*wp.lock() == " << *wp.lock() << std::endl;
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    wp.reset();
    std::cout << "wp.expired() == " << std::boolalpha
        << wp.expired() << std::endl;

    return (0);
}

```

```Output
*wp.lock() == 5
wp.expired() == false
wp.expired() == true
```

## <a name="swap"></a>  swap

2 つの `weak_ptr` オブジェクトを交換します。

```cpp
void swap(weak_ptr& wp);
```

### <a name="parameters"></a>パラメーター

`wp` スワップするウィーク ポインター。

### <a name="remarks"></a>コメント

このメンバー関数は、最初に `*this` が指し示しその後 `wp` が指し示したリソースと、最初に `wp` が指し示しその後 `*this` が指し示したリソースを残します。 この関数はこれら 2 つのリソースの参照数を変更せず、例外をスローしません。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_swap.cpp
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

## <a name="use_count"></a>  use_count

指定された `shared_ptr` オブジェクトの数をカウントします。

```cpp
long use_count() const;
```

### <a name="remarks"></a>コメント

このメンバー関数は、`*this` が指し示すリソースを所有する `shared_ptr` オブジェクトの数を返します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_use_count.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    std::shared_ptr<int> sp2(sp1);
    std::cout << "wp.use_count() == "
        << wp.use_count() << std::endl;

    return (0);
}

```

```Output
wp.use_count() == 1
wp.use_count() == 2
```

## <a name="weak_ptr"></a>  weak_ptr

`weak_ptr` を構築します。

```cpp
weak_ptr();

weak_ptr(const weak_ptr& wp);

template <class Other>
weak_ptr(const weak_ptr<Other>& wp);

template <class Other>
weak_ptr(const shared_ptr<Other>& sp);
```

### <a name="parameters"></a>パラメーター

`Other` 引数の共有/ウィーク ポインターによって制御される型。

`wp` コピーするウィーク ポインター。

`sp` 共有ポインターにコピーします。

### <a name="remarks"></a>コメント

コンストラクターはそれぞれ、オペランド シーケンスで指定されたリソースを指し示すオブジェクトを構築します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_construct.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

int main()
{
    std::weak_ptr<int> wp0;
    std::cout << "wp0.expired() == " << std::boolalpha
        << wp0.expired() << std::endl;

    std::shared_ptr<int> sp1(new int(5));
    std::weak_ptr<int> wp1(sp1);
    std::cout << "*wp1.lock() == "
        << *wp1.lock() << std::endl;

    std::weak_ptr<int> wp2(wp1);
    std::cout << "*wp2.lock() == "
        << *wp2.lock() << std::endl;

    return (0);
}

```

```Output
wp0.expired() == true
*wp1.lock() == 5
*wp2.lock() == 5
```

## <a name="see-also"></a>関連項目

[shared_ptr クラス](../standard-library/shared-ptr-class.md)<br/>
