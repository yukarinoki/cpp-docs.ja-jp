---
title: is_bind_expression クラス
ms.date: 11/04/2016
f1_keywords:
- functional/std::is_bind_expression
helpviewer_keywords:
- is_bind_expression class
ms.assetid: 0715f9e9-2239-4778-a1cf-2c21f49dfd47
ms.openlocfilehash: f547b6f74a86612174cb0f510870171158678f7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519419"
---
# <a name="isbindexpression-class"></a>is_bind_expression クラス

`bind` の呼び出しによって型が生成されたかどうかテストします。

## <a name="syntax"></a>構文

テンプレート<class Ty>構造体 is_bind_expression static const bool {value}; です。

## <a name="remarks"></a>Remarks

型 `Ty` が `bind` への呼び出しによって返される型の場合、定数メンバー `value` は true です。それ以外の場合は false です。

## <a name="example"></a>例

```cpp
// std__functional__is_bind_expression.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

void square(double x)
{
    std::cout << x << "^2 == " << x * x << std::endl;
}

template<class Expr>
void test_for_bind(const Expr&)
{
    std::cout << std::is_bind_expression<Expr>::value << std::endl;
}

int main()
{
    test_for_bind(3.0 * 3.0);
    test_for_bind(std::bind(square, 3));

    return (0);
}
```

```Output
0
1
```

## <a name="requirements"></a>必要条件

**ヘッダー:** \<functional>

**名前空間:** std

## <a name="see-also"></a>関連項目

[bind](../standard-library/functional-functions.md#bind)<br/>
