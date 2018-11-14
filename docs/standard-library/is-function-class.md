---
title: is_function クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is
helpviewer_keywords:
- is_function class
- is
ms.assetid: e5c0dbcd-829b-415f-853f-8c5be47c5040
ms.openlocfilehash: 0d2559ca6d864a23c5949bcddee8790df4b2bb65
ms.sourcegitcommit: afd6fac7c519dbc47a4befaece14a919d4e0a8a2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2018
ms.locfileid: "51523045"
---
# <a name="isfunction-class"></a>is_function クラス

型が関数型であるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_function;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*は関数型、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_function.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

struct functional
    {
    int f();
    };

int main()
    {
    std::cout << "is_function<trivial> == " << std::boolalpha
        << std::is_function<trivial>::value << std::endl;
    std::cout << "is_function<functional> == " << std::boolalpha
        << std::is_function<functional>::value << std::endl;
    std::cout << "is_function<float()> == " << std::boolalpha
        << std::is_function<float()>::value << std::endl;

    return (0);
    }
```

```Output
is_function<trivial> == false
is_function<functional> == false
is_function<float()> == true
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_object クラス](../standard-library/is-object-class.md)<br/>
