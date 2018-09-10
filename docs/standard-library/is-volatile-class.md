---
title: is_volatile クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_volatile
dev_langs:
- C++
helpviewer_keywords:
- is_volatile class
- is_volatile
ms.assetid: 54922e8a-db4e-4cae-8931-b3352f0b8d3b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d35b28025370f7f8dc66c83a12a8e6142e6085ef
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44104278"
---
# <a name="isvolatile-class"></a>is_volatile クラス

型が volatile かどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_volatile;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持*Ty*は`volatile-qualified`します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_volatile.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_volatile<trivial> == " << std::boolalpha
        << std::is_volatile<trivial>::value << std::endl;
    std::cout << "is_volatile<volatile trivial> == " << std::boolalpha
        << std::is_volatile<volatile trivial>::value << std::endl;
    std::cout << "is_volatile<int> == " << std::boolalpha
        << std::is_volatile<int>::value << std::endl;
    std::cout << "is_volatile<volatile int> == " << std::boolalpha
        << std::is_volatile<volatile int>::value << std::endl;

    return (0);
    }

```

```Output
is_volatile<trivial> == false
is_volatile<volatile trivial> == true
is_volatile<int> == false
is_volatile<volatile int> == true
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_const クラス](../standard-library/is-const-class.md)<br/>
