---
title: add_const クラス
ms.date: 11/04/2016
f1_keywords:
- type_traits/std::add_const
helpviewer_keywords:
- add_const class
- add_const
ms.assetid: 1262a1eb-8c9c-4dd6-9f43-88ba280182f1
ms.openlocfilehash: dc457fd4efba538e96200f7f42f84a73fc1b5228
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62411241"
---
# <a name="addconst-class"></a>add_const クラス

型から const 型を作成します。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct add_const;
```

### <a name="parameters"></a>パラメーター

*Ty*<br/>
変更する型。

## <a name="remarks"></a>Remarks

型修飾子のインスタンスを保持する、修飾型である*Ty*場合*Ty*の参照、関数、または const で修飾された型では、それ以外の場合は、`const Ty`します。

## <a name="example"></a>例

```cpp
// std__type_traits__add_const.cpp
// compile with: /EHsc
#include <type_traits>
#include <iostream>

int main()
{
    std::add_const<int>::type *p = (const int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_const<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_const<int> == int
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_const クラス](../standard-library/remove-const-class.md)<br/>
