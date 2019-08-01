---
title: weak_ptr クラス
ms.date: 07/29/2019
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
ms.openlocfilehash: d4ba30f737bc570a4ee700b3a317b5feebe8a50a
ms.sourcegitcommit: 725e86dabe2901175ecc63261c3bf05802dddff4
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/31/2019
ms.locfileid: "68682406"
---
# <a name="weakptr-class"></a>weak_ptr クラス

関連付けの弱いポインターをラップします。

## <a name="syntax"></a>構文

```cpp
template<class T> class weak_ptr;
```

### <a name="parameters"></a>パラメーター

*\T*\
ウィーク ポインターによって制御される型。

## <a name="remarks"></a>Remarks

このテンプレートクラスは、1つまたは複数の[shared_ptr](shared-ptr-class.md)オブジェクトによって管理されるリソースを指すオブジェクトを表します。 リソース`weak_ptr`をポイントするオブジェクトは、リソースの参照カウントに影響しません。 そのリソースを`shared_ptr`管理する最後のオブジェクトが破棄されると、そのリソースを指す`weak_ptr`オブジェクトがある場合でも、リソースが解放されます。 この動作は、データ構造の循環を避けるために不可欠です。

`weak_ptr` オブジェクトは、リソースを所有する `shared_ptr` オブジェクトから構築された場合や、リソースを指し示す `weak_ptr` オブジェクトから構築された場合、またはリソースが [operator=](#op_eq) を使って割り当てられた場合に、そのリソースを指し示します。 オブジェクト`weak_ptr`は、そのオブジェクトが指しているリソースへの直接アクセスを提供しません。 そのリソースを使用する必要があるコードは、メンバー関数 [lock](#lock) を呼び出すことによって作成された、そのリソースを所有する `shared_ptr` オブジェクトを介してそのリソースを使用します。 リソースを所有するすべて`shared_ptr`のオブジェクトが破棄されているため、オブジェクトの有効期限は切れています。`weak_ptr` 有効期限の切れた `weak_ptr` オブジェクトで `lock` を呼び出すと、空の shared_ptr オブジェクトが作成されます。

空の weak_ptr オブジェクトは、リソースを指しておらず、コントロールブロックも持ちません。 そのメンバー関数 `lock` は、空の shared_ptr オブジェクトを返します。

循環は、`shared_ptr` オブジェクトによって制御される複数のリソースで、相互に参照し合う `shared_ptr` オブジェクトが保持されているときに発生します。 たとえば、3 つの要素から成るリンク リストがあるとします。先頭のノード `N0` が 2 番目のノード `N1` を所有する `shared_ptr` オブジェクトを保持し、2 番目のノードが 3 番目のノード `N2` を所有する `shared_ptr` オブジェクトを保持し、次に、3 番目のノードが先頭のノード `N0` を所有する `shared_ptr` オブジェクトを保持しているとすると、ループが閉じた状態になり、このリストは循環リンク リストになります。 この場合、参照カウントはゼロにならず、サイクル内のノードは解放されません。 この循環を解消するためには、最後のノード `N2` が、`shared_ptr` オブジェクトではなく、`N0` を指し示す `weak_ptr` オブジェクトを保持する必要があります。 オブジェクトが`weak_ptr`所有`N0`していないため`N0`、の参照カウントには影響しません。また、ヘッドノードへのプログラムの最後の参照が破棄されると、リスト内のノードも破棄されます。

## <a name="members"></a>メンバー

|||
|-|-|
| **コンストラクター** | |
|[weak_ptr](#weak_ptr)|`weak_ptr` を構築します。|
| **デストラクター** | |
|[~ weak_ptr](#tilde-weak_ptr)|`weak_ptr` を構築します。|
| **Typedefs** | |
|[element_type](#element_type)|要素の型。|
| **メンバー関数** | |
|[expired](#expired)|所有権の有効期限が切れているかどうかをテストします。|
|[lock](#lock)|リソースの排他的所有権を取得します。|
|[owner_before](#owner_before)|この`weak_ptr`が、指定されたポインターの前 (またはそれより小さい) に順序付けされている場合、 **true**を返します。|
|[reset](#reset)|所有されたリソースを解放します。|
|[swap](#swap)|2 つの `weak_ptr` オブジェクトを交換します。|
|[use_count](#use_count)|オブジェクトの`shared_ptr`数をカウントします。|
| **演算子** | |
|[operator=](#op_eq)|所有されたリソースを置換します。|

## <a name="element_type"></a>element_type

要素の型。

```cpp
typedef T element_type; // through C++17
using element_type = remove_extent_t<T>; // C++20
```

### <a name="remarks"></a>Remarks

この型は、テンプレート パラメーター `T` のシノニムです。

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

## <a name="expired"></a>終了

所有権の有効期限が切れているかどうか、つまり、参照先のオブジェクトが削除されたかどうかをテストします。

```cpp
bool expired() const noexcept;
```

### <a name="remarks"></a>Remarks

このメンバー関数は、が`*this`期限切れになった場合は**true**を返し、それ以外の場合は**false**を返します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_expired.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="lock"></a>制限

リソースの`shared_ptr`所有権を共有するを取得します。

```cpp
shared_ptr<T> lock() const noexcept;
```

### <a name="remarks"></a>Remarks

の有効期限が切れた場合、この`*this`メンバー関数は空の [shared_ptr](shared-ptr-class.md) オブジェクト`shared_ptr<T>`を返します。それ以外`*this`の場合は、が指し示すリソースを所有するオブジェクトを返します。 の`expired() ? shared_ptr<T>() : shared_ptr<T>(*this)`アトミック実行に相当する値を返します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_lock.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="op_eq"></a>operator =

所有されたリソースを置換します。

```cpp
weak_ptr& operator=(const weak_ptr& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const weak_ptr<Other>& ptr) noexcept;

template <class Other>
weak_ptr& operator=(const shared_ptr<Other>& ptr) noexcept;
```

### <a name="parameters"></a>パラメーター

*他の*\
引数の共有ポインターまたはウィークポインターによって制御される型。

*ポインター*\
コピーする弱ポインターまたは共有ポインター。

### <a name="remarks"></a>Remarks

すべての演算子は、現在が指して`*this`いるリソースを解放し、 *ptr*によって名前`*this`が付けられたリソースの所有権をに割り当てます。 操作が失敗した場合は`*this` 、変更されません。 各演算子には、と同じ`weak_ptr(ptr).swap(*this)`効果があります。

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

## <a name="owner_before"></a>owner_before

この`weak_ptr`が、指定されたポインターの前 (またはそれより小さい) に順序付けされている場合、 **true**を返します。

```cpp
template <class Other>
bool owner_before(const shared_ptr<Other>& ptr) const noexcept;

template <class Other>
bool owner_before(const weak_ptr<Other>& ptr) const noexcept;
```

### <a name="parameters"></a>パラメーター

*ポインター*\
またはのいずれかへの左辺値参照。 `weak_ptr` `shared_ptr`

### <a name="remarks"></a>Remarks

テンプレートメンバー関数は、が*ptr*の前にある場合`*this`に**true**を返します。

## <a name="reset"></a>解除

所有されているリソースを解放します。

```cpp
void reset() noexcept;
```

### <a name="remarks"></a>Remarks

このメンバー関数は、が指す`*this`リソースを解放し、空`weak_ptr`のオブジェクトに変換`*this`します。

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

## <a name="swap"></a>フォト

2 つの `weak_ptr` オブジェクトを交換します。

```cpp
void swap(weak_ptr& wp) noexcept;
```

また、特殊化も含まれています。

```cpp
template<class T>
void swap(weak_ptr<T>& a, weak_ptr<T>& b) noexcept;
```

### <a name="parameters"></a>パラメーター

*wp*\
交換するウィーク ポインター。

### <a name="remarks"></a>Remarks

`swap`の後、は、もともとによって`*this`ポイントされているリソースが*wp*によって参照され、もともと*wp*に`*this`よって参照されていたリソースがによってポイントされます。 関数は、2つのリソースの参照カウントを変更せず、例外もスローしません。 テンプレートの特殊化の効果は、に`a.swap(b)`相当します。

### <a name="example"></a>例

```cpp
// std__memory__weak_ptr_swap.cpp
// compile with: /EHsc
#include <memory>
#include <iostream>

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

## <a name="use_count"></a>use_count

共有リソースを所有`shared_ptr`するオブジェクトの数をカウントします。

```cpp
long use_count() const noexcept;
```

### <a name="remarks"></a>Remarks

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

## <a name="weak_ptr"></a>weak_ptr

`weak_ptr` を構築します。

```cpp
constexpr weak_ptr() noexcept;

weak_ptr(const weak_ptr& wp) noexcept;

weak_ptr(weak_ptr&& wp) noexcept;

template <class Other>
weak_ptr(const weak_ptr<Other>& wp) noexcept;

template <class Other>
weak_ptr(weak_ptr<Other>&& sp) noexcept;

template <class Other>
weak_ptr(const shared_ptr<Other>& sp) noexcept;
```

### <a name="parameters"></a>パラメーター

*他の*\
引数の共有ポインターまたはウィーク ポインターによって制御される型。 これらのコンストラクターは、_他の\*_ がと`element_type*`互換性がない限り、オーバーロードの解決に関与しません。

*wp*\
コピーするウィーク ポインター。

*プロセッサー*\
コピーする共有ポインター。

### <a name="remarks"></a>Remarks

既定のコンストラクターは、空`weak_ptr`のオブジェクトを構築します。 引数ポインターが空の場合、引数を受け取る`weak_ptr`コンストラクターはそれぞれ、空のオブジェクトを構築します。 それ以外の場合は`weak_ptr` 、引数で指定されたリソースを指すオブジェクトを構築します。 共有オブジェクトの参照カウントは変更されません。

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

## <a name="tilde-weak_ptr"></a>~ weak_ptr

`weak_ptr` を破棄します。

```cpp
~weak_ptr();
```

### <a name="remarks"></a>Remarks

デストラクターはこれ`weak_ptr`を破棄しますが、格納されているポインターが指すオブジェクトの参照カウントには影響しません。

## <a name="see-also"></a>関連項目

[ヘッダー ファイル リファレンス](cpp-standard-library-header-files.md)\
[\<memory>](memory.md)\
[shared_ptr クラス](shared-ptr-class.md)
