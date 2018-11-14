---
title: is_floating_point クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_floating_point
helpviewer_keywords:
- is_floating_point class
- is_floating_point
ms.assetid: 070679c1-115b-4ee4-8ab7-f52e5d9e157f
ms.openlocfilehash: 242c55cfa6b62e49aa5b73de0aa1a353c16827f9
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51517736"
---
# <a name="isfloatingpoint-class"></a>is_floating_point クラス

型が浮動小数点かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_floating_point;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*が浮動小数点型または`cv-qualified`形式の浮動小数点型、それ以外の場合は false を保持します。

A の 1 つは、浮動小数点型**float**、**二重**、または**long double**します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_floating_point.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_floating_point<trivial> == " << std::boolalpha
        << std::is_floating_point<trivial>::value << std::endl;
    std::cout << "is_floating_point<int> == " << std::boolalpha
        << std::is_floating_point<int>::value << std::endl;
    std::cout << "is_floating_point<float> == " << std::boolalpha
        << std::is_floating_point<float>::value << std::endl;

    return (0);
    }
```

```Output
is_floating_point<trivial> == false
is_floating_point<int> == false
is_floating_point<float> == true
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_integral クラス](../standard-library/is-integral-class.md)<br/>
