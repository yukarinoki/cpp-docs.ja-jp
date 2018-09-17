---
title: _1 オブジェクト |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- _1
- std::_1
- functional/std::_1
dev_langs:
- C++
helpviewer_keywords:
- _1 object
ms.assetid: 30c3c480-ff31-4708-94be-7d0d65f243c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 156eca047946ad13b1e4f09057edceb9f0bc6b34
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/17/2018
ms.locfileid: "45719187"
---
# <a name="1-object"></a>_1 オブジェクト

置き換え可能な引数のプレースホルダーです。

## <a name="syntax"></a>構文

```cpp
namespace placeholders {
    extern unspecified _1,
    _2, ... _M
} // namespace placeholders (within std)
```

## <a name="remarks"></a>Remarks

オブジェクト`_1, _2, ... _M`指定するプレース ホルダーは、1 番目、…、番目の引数、関数呼び出しによって返されるオブジェクトでそれぞれ[バインド](../standard-library/functional-functions.md#bind)します。 bind 式が評価されるときに N 番目の引数が挿入される場所を指定するには、`_N` を使用します。

この実装では、`M` の値は 20 です。

## <a name="example"></a>例

```cpp
// std__functional_placeholder.cpp
// compile with: /EHsc
#include <functional>
#include <algorithm>
#include <iostream>

using namespace std::placeholders;

void square(double x)
    {
    std::cout << x << "^2 == " << x * x << std::endl;
    }

void product(double x, double y)
    {
    std::cout << x << "*" << y << " == " << x * y << std::endl;
    }

int main()
    {
    double arg[] = {1, 2, 3};

    std::for_each(&arg[0], &arg[3], square);
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(product, _1, 2));
    std::cout << std::endl;

    std::for_each(&arg[0], &arg[3], std::bind(square, _1));

    return (0);
    }

```

```Output
1^2 == 1
2^2 == 4
3^2 == 9

1*2 == 2
2*2 == 4
3*2 == 6

1^2 == 1
2^2 == 4
3^2 == 9
```

## <a name="requirements"></a>要件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[bind](../standard-library/functional-functions.md#bind)<br/>
[is_placeholder クラス](../standard-library/is-placeholder-class.md)<br/>
