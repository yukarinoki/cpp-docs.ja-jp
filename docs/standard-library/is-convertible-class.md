---
title: is_convertible クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_convertible
helpviewer_keywords:
- is_convertible class
- is_convertible
ms.assetid: 75614008-1894-42ea-bd57-974399628536
ms.openlocfilehash: 1df87299d0b06ccfd2bef05bab89a9241f27d57d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50583561"
---
# <a name="isconvertible-class"></a>is_convertible クラス

一方の型をもう一方の型に変換できるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class From, class To>
struct is_convertible;
```

### <a name="parameters"></a>パラメーター

*From*<br/>
変換前の型。

*Ty*<br/>
変換後の型。

## <a name="remarks"></a>Remarks

`To to = from;` という式が正しい形式である場合、型述語のインスタンスは true を保持します (`from` は型 `From` のオブジェクト)。

## <a name="example"></a>例

```cpp
// std__type_traits__is_convertible.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_convertible<trivial, int> == " << std::boolalpha
        << std::is_convertible<trivial, int>::value << std::endl;
    std::cout << "is_convertible<trivial, trivial> == " << std::boolalpha
        << std::is_convertible<trivial, trivial>::value << std::endl;
    std::cout << "is_convertible<char, int> == " << std::boolalpha
        << std::is_convertible<char, int>::value << std::endl;

    return (0);
    }

```

```Output
is_convertible<trivial, int> == false
is_convertible<trivial, trivial> == true
is_convertible<char, int> == true
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_base_of クラス](../standard-library/is-base-of-class.md)<br/>
