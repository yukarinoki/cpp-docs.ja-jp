---
description: '詳細情報: add_cv クラス'
title: add_cv クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_cv
helpviewer_keywords:
- add_cv class
- add_cv
ms.assetid: a5572c78-a097-45d7-b476-ed4876889dea
ms.openlocfilehash: bc25efd879a27b3d3af2e5f4db8dd74fafa3fb45
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319932"
---
# <a name="add_cv-class"></a>add_cv クラス

型 **`const volatile`** から型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class T>
struct add_cv;

template <class T>
using add_cv_t = typename add_cv<T>::type;
```

### <a name="parameters"></a>パラメーター

*\T*\
変更する型。

## <a name="remarks"></a>解説

変更後の型のインスタンスには、 `add_cv<T>` `type` **`typedef`** [add_volatile](add-volatile-class.md)と [add_const](add-const-class.md)の両方によって変更された *t* と等価なメンバーがあります。ただし、既に cv 修飾子があるか、参照であるか、または関数である場合を除きます。

`add_cv_t<T>` ヘルパー型は、`add_cv<T>` メンバー typedef `type` にアクセスするショートカットです。

## <a name="example"></a>例

```cpp
// add_cv.cpp
// compile by using: cl /EHsc /W4 add_cv.cpp
#include <type_traits>
#include <iostream>

struct S {
    void f() {
        std::cout << "invoked non-cv-qualified S.f()" << std::endl;
    }
    void f() const {
        std::cout << "invoked const S.f()" << std::endl;
    }
    void f() volatile {
        std::cout << "invoked volatile S.f()" << std::endl;
    }
    void f() const volatile {
        std::cout << "invoked const volatile S.f()" << std::endl;
    }
};

template <class T>
void invoke() {
    T t;
    ((T *)&t)->f();
}

int main()
{
    invoke<S>();
    invoke<std::add_const<S>::type>();
    invoke<std::add_volatile<S>::type>();
    invoke<std::add_cv<S>::type>();
}
```

```Output
invoked non-cv-qualified S.f()
invoked const S.f()
invoked volatile S.f()
invoked const volatile S.f()
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](type-traits.md)\
[remove_const クラス](remove-const-class.md)\
[remove_volatile クラス](remove-volatile-class.md)
