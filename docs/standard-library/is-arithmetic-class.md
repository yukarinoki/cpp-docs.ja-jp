---
description: '詳細情報: is_arithmetic クラス'
title: is_arithmetic クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_arithmetic
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
ms.openlocfilehash: 75673950a162b34815db297a3012fa7152e61375
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323874"
---
# <a name="is_arithmetic-class"></a>is_arithmetic クラス

種類が演算かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* が算術型、つまり、整数型または浮動小数点型、またはそのいずれかの形式である場合、型述語のインスタンスは true を保持し `cv-qualified` ます。それ以外の場合は、false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_arithmetic.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_arithmetic<trivial> == " << std::boolalpha
        << std::is_arithmetic<trivial>::value << std::endl;
    std::cout << "is_arithmetic<int> == " << std::boolalpha
        << std::is_arithmetic<int>::value << std::endl;
    std::cout << "is_arithmetic<float> == " << std::boolalpha
        << std::is_arithmetic<float>::value << std::endl;

    return (0);
    }
```

```Output
is_arithmetic<trivial> == false
is_arithmetic<int> == true
is_arithmetic<float> == true
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_floating_point クラス](../standard-library/is-floating-point-class.md)\
[is_integral クラス](../standard-library/is-integral-class.md)
