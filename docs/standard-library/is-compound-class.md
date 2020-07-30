---
title: is_compound クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_compound
helpviewer_keywords:
- is_compound class
- is_compound
ms.assetid: bdad1167-cf3f-4f37-8321-62a5df159ead
ms.openlocfilehash: ae2e3c66b3abf22bbefbcb0fcd3292f0a3dbdbe2
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215713"
---
# <a name="is_compound-class"></a>is_compound クラス

指定した型が基本型でないかどうかを調べます。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_compound;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

**`false`** *Ty*の型が基本型である場合 (つまり[is_fundamental](../standard-library/is-fundamental-class.md)がを保持している場合)、型述語のインスタンスはを保持 \<Ty> **`true`** します。それ以外の場合はを保持 **`true`** します。 したがって、 **`true`** *Ty*が配列型、関数型、 **`void`** またはオブジェクトまたは関数へのポインター、参照、クラス、共用体、列挙体、非静的クラスメンバーへのポインター、またはそのうちの1つの*cv で修飾*された形式である場合、述語はを保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_compound.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

struct trivial
    {
    int val;
    };

int main()
    {
    std::cout << "is_compound<trivial> == " << std::boolalpha
        << std::is_compound<trivial>::value << std::endl;
    std::cout << "is_compound<int[]> == " << std::boolalpha
        << std::is_compound<int[]>::value << std::endl;
    std::cout << "is_compound<int()> == " << std::boolalpha
        << std::is_compound<int()>::value << std::endl;
    std::cout << "is_compound<int&> == " << std::boolalpha
        << std::is_compound<int&>::value << std::endl;
    std::cout << "is_compound<void *> == " << std::boolalpha
        << std::is_compound<void *>::value << std::endl;
    std::cout << "is_compound<int> == " << std::boolalpha
        << std::is_compound<int>::value << std::endl;

    return (0);
    }
```

```Output
is_compound<trivial> == true
is_compound<int[]> == true
is_compound<int()> == true
is_compound<int&> == true
is_compound<void *> == true
is_compound<int> == false
```

## <a name="requirements"></a>必要条件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_class クラス](../standard-library/is-class-class.md)
