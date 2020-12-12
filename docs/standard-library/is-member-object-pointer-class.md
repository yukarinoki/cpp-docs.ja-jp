---
description: '詳細情報: is_member_object_pointer クラス'
title: is_member_object_pointer クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::is_member_object_pointer
helpviewer_keywords:
- is_member_object_pointer class
- is_member_object_pointer
ms.assetid: 64f9cdf3-4621-4310-a076-a7bc986926b9
ms.openlocfilehash: bf98bfa4017730a212f99849bde552ceb67625b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230934"
---
# <a name="is_member_object_pointer-class"></a>is_member_object_pointer クラス

型がメンバー オブジェクトへのポインターであるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_member_object_pointer;
```

### <a name="parameters"></a>パラメーター

*~*\
照会する型。

## <a name="remarks"></a>解説

型 *Ty* がメンバーオブジェクトへのポインターまたはメンバーオブジェクトへのポインターである場合、型述語のインスタンスは true を保持し `cv-qualified` ます。それ以外の場合は、false を保持します。 `is_member_object_pointer` *Ty* がメンバー関数へのポインターである場合、は false を保持することに注意してください。

## <a name="example"></a>例

```cpp
// std__type_traits__is_member_object_pointer.cpp
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
    std::cout << "is_member_object_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_object_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_object_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_object_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_object_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_object_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }
```

```Output
is_member_object_pointer<trivial *> == false
is_member_object_pointer<int trivial::*> == true
is_member_object_pointer<int (functional::*)()> == false
```

## <a name="requirements"></a>要件

**ヘッダー:**\<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)\
[is_member_pointer クラス](../standard-library/is-member-pointer-class.md)
