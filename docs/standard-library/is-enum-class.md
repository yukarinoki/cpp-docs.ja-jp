---
title: is_enum クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_enum
helpviewer_keywords:
- is_enum class
- is_enum
ms.assetid: df3b00b7-4f98-4b3a-96ce-10ad958ee69c
ms.openlocfilehash: 95b36d512f4fb6501f5ae00d8f0dd49520613558
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50507654"
---
# <a name="isenum-class"></a>is_enum クラス

型が列挙型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_enum;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は列挙型、または`cv-qualified`形式の列挙型、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_enum.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

enum color {
    red, greed, blue};

int main()
    {
    std::cout << "is_enum<trivial> == " << std::boolalpha
        << std::is_enum<trivial>::value << std::endl;
    std::cout << "is_enum<color> == " << std::boolalpha
        << std::is_enum<color>::value << std::endl;
    std::cout << "is_enum<int> == " << std::boolalpha
        << std::is_enum<int>::value << std::endl;

    return (0);
    }

```

```Output
is_enum<trivial> == false
is_enum<color> == true
is_enum<int> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_integral クラス](../standard-library/is-integral-class.md)<br/>
