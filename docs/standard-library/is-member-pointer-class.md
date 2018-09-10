---
title: is_member_pointer クラス | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::is_member_pointer
dev_langs:
- C++
helpviewer_keywords:
- is_member_pointer class
- is_member_pointer
ms.assetid: da07ff4e-9ee0-4baa-ad93-1741f10913d1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bdc179413b3e5d77646be4ccb98f23bcff407fb7
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110267"
---
# <a name="ismemberpointer-class"></a>is_member_pointer クラス

型がメンバーへのポインターであるかどうかをテストします。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct is_member_pointer;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
照会する型。

## <a name="remarks"></a>Remarks

場合、型述語のインスタンスは true を保持型*Ty*がメンバー関数へのポインターまたはメンバーのオブジェクトへのポインターまたは`cv-qualified`形式のうち 1 つ、それ以外の場合は false を保持します。

## <a name="example"></a>例

```cpp
// std__type_traits__is_member_pointer.cpp
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
    std::cout << "is_member_pointer<trivial *> == "
        << std::boolalpha
        << std::is_member_pointer<trivial *>::value
        << std::endl;
    std::cout << "is_member_pointer<int trivial::*> == "
        << std::boolalpha
        << std::is_member_pointer<int trivial::*>::value
        << std::endl;
    std::cout << "is_member_pointer<int (functional::*)()> == "
        << std::boolalpha
        << std::is_member_pointer<int (functional::*)()>::value
        << std::endl;

    return (0);
    }

```

```Output
is_member_pointer<trivial *> == false
is_member_pointer<int trivial::*> == true
is_member_pointer<int (functional::*)()> == true
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[is_member_function_pointer クラス](../standard-library/is-member-function-pointer-class.md)<br/>
[is_member_object_pointer クラス](../standard-library/is-member-object-pointer-class.md)<br/>
[is_pointer クラス](../standard-library/is-pointer-class.md)<br/>
