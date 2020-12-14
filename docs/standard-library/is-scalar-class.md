---
description: '詳細情報: is_scalar クラス'
title: is_scalar クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_scalar
helpviewer_keywords:
- is_scalar class
- is_scalar
ms.assetid: a0cdfc9a-f27e-4808-890f-6ed7942db60c
ms.openlocfilehash: 34d998536d3ad1843b44de5ad64c8b6a664895d9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247671"
---
# <a name="is_scalar-class"></a>is_scalar クラス

型がスカラーかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_scalar;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* が整数型、浮動小数点型、列挙型、ポインター型、またはメンバー型へのポインター、またはそのいずれかの形式である場合、型述語のインスタンスは true を保持し `cv-qualified` ます。それ以外の場合は、false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_scalar.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_scalar<trivial> == " << std::boolalpha
        << std::is_scalar<trivial>::value << std::endl;
    std::cout << "is_scalar<trivial *> == " << std::boolalpha
        << std::is_scalar<trivial *>::value << std::endl;
    std::cout << "is_scalar<int> == " << std::boolalpha
        << std::is_scalar<int>::value << std::endl;
    std::cout << "is_scalar<float> == " << std::boolalpha
        << std::is_scalar<float>::value << std::endl;

    return (0);
    }
```

```Output
is_scalar<trivial> == false
is_scalar<trivial *> == true
is_scalar<int> == true
is_scalar<float> == true
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_compound クラス](../standard-library/is-compound-class.md)
