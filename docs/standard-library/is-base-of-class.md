---
description: '詳細情報: is_base_of クラス'
title: is_base_of クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_base_of
helpviewer_keywords:
- is_base_of class
- is_base_of
ms.assetid: 436f6213-1d4c-4ffc-a588-fc7c4887dd86
ms.openlocfilehash: 6cb2b55a6df687fbb7da74ca3c696a8a9b0ffbad
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231265"
---
# <a name="is_base_of-class"></a>is_base_of クラス

一方の型がもう一方の型の基底クラスであるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Base, class Derived>
struct is_base_of;
```

### <a name="parameters"></a>パラメーター

*常用*\
テスト対象の基底クラス。

*導出*\
テスト対象の派生型。

## <a name="remarks"></a>解説

型の述語のインスタンスは、型の *ベース* が *派生* 型の基底クラスである場合は true を保持します。それ以外の場合は、false を保持します。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

struct base
    {
    int val;
    };

struct derived
    : public base
    {
    };

int main()
    {
    std::cout << "is_base_of<base, base> == " << std::boolalpha
        << std::is_base_of<base, base>::value << std::endl;
    std::cout << "is_base_of<base, derived> == " << std::boolalpha
        << std::is_base_of<base, derived>::value << std::endl;
    std::cout << "is_base_of<derived, base> == " << std::boolalpha
        << std::is_base_of<derived, base>::value << std::endl;

    return (0);
    }
```

```Output
is_base_of<base, base> == true
is_base_of<base, derived> == true
is_base_of<derived, base> == false
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_convertible クラス](../standard-library/is-convertible-class.md)
