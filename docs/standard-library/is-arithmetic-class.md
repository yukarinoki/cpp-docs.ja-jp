---
title: is_arithmetic クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_arithmetic
dev_langs:
- C++
helpviewer_keywords:
- is_arithmetic class
- is_arithmetic
ms.assetid: ea427b7e-0141-4a04-848f-561054c53001
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 161551747455bae1347e5059ec3afffd2649294c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33845298"
---
# <a name="isarithmetic-class"></a>is_arithmetic クラス

種類が演算かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_arithmetic;
```

### <a name="parameters"></a>パラメーター

`Ty` 照会する型。

## <a name="remarks"></a>コメント

型述語のインスタンスは、型 `Ty` が演算型 (つまり、整数型または浮動小数点型)、またはそのいずれかの `cv-qualified` 形式の場合は true を保持し、それ以外の場合は false を保持します。

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

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_floating_point クラス](../standard-library/is-floating-point-class.md)<br/>
[is_integral クラス](../standard-library/is-integral-class.md)<br/>
