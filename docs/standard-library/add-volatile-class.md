---
title: add_volatile クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- type_traits/std::add_volatile
dev_langs:
- C++
helpviewer_keywords:
- add_volatile class
- add_volatile
ms.assetid: cde57277-d764-402d-841e-97611ebaab14
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 39740894e9422c2aec90c3598b0e45965e8ddba7
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100742"
---
# <a name="addvolatile-class"></a>add_volatile クラス

により、**揮発性**指定した型からの型。

## <a name="syntax"></a>構文

```cpp
template <class Ty>
struct add_volatile;

template <class T>
using add_volatile_t = typename add_volatile<T>::type;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
変更する型。

## <a name="remarks"></a>Remarks

インスタンス`add_volatile<T>`メンバーがある**typedef** `type`つまり*T*場合*T*が参照、関数の場合、または volatile で修飾された型、それ以外の場合**揮発性** *T*します。エイリアス`add_volatile_t`メンバーにアクセスするショートカット**typedef** `type`します。

## <a name="example"></a>例

```cpp
#include <type_traits>
#include <iostream>

int main()
{
    std::add_volatile_t<int> *p = (volatile int *)0;

    p = p;  // to quiet "unused" warning
    std::cout << "add_volatile<int> == "
        << typeid(*p).name() << std::endl;

    return (0);
}
```

```Output
add_volatile<int> == int
```

## <a name="requirements"></a>要件

**ヘッダー:** \<type_traits>

**名前空間:** std

## <a name="see-also"></a>関連項目

[<type_traits>](../standard-library/type-traits.md)<br/>
[remove_volatile クラス](../standard-library/remove-volatile-class.md)<br/>
