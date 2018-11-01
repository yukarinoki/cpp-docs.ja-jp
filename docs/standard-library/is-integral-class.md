---
title: is_integral クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_integral
helpviewer_keywords:
- is_integral class
- is_integral
ms.assetid: fe9279d0-4495-4e88-bf23-153cc6602397
ms.openlocfilehash: 89655517c73f7c84f48f8b85a1c119674950ebeb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50556624"
---
# <a name="isintegral-class"></a>is_integral クラス

型が整数かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_integral;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は整数の型のいずれかまたは`cv-qualified`形式のいずれかの整数型、それ以外の場合は false を保持します。

整数型は、のいずれかの**bool**、 **char**、 **unsigned char**、 **char を署名**、 **wchar_t**、 **短い**、 **unsigned short**、 **int**、**符号なし int**、**長い**、および**unsigned long**します。 さらに、それらを提供するコンパイラでは、整数型のいずれかできます**long**、 **unsigned long long 型**、 **_ _int64**、および**符号なし _ _int64**.

## <a name="example"></a>例

```cpp
// std__type_traits__is_integral.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_integral<trivial> == " << std::boolalpha
        << std::is_integral<trivial>::value << std::endl;
    std::cout << "is_integral<int> == " << std::boolalpha
        << std::is_integral<int>::value << std::endl;
    std::cout << "is_integral<float> == " << std::boolalpha
        << std::is_integral<float>::value << std::endl;

    return (0);
    }

```

```Output
is_integral<trivial> == false
is_integral<int> == true
is_integral<float> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_enum クラス](../standard-library/is-enum-class.md)<br/>
[is_floating_point クラス](../standard-library/is-floating-point-class.md)<br/>
