---
title: _ _restrict |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- __restrict_cpp
dev_langs:
- C++
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3d9754f8b0b218fc4d627eb0e27504e8521bf776
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076438"
---
# <a name="restrict"></a>__restrict

ように、 **_ _declspec ([制限](../cpp/restrict.md))** 修飾子、 **_ _restrict**キーワードは、シンボルがエイリアス化された現在のスコープ内ではないことを示します。 **_ _Restrict**キーワードとは異なります、`__declspec ( restrict )`修飾子は、次の方法で。

- **_ _Restrict**キーワードは、変数にのみ有効ですし、`__declspec ( restrict )`関数宣言と定義でのみ有効です。

- **_ _restrict**のような**制限**C99 仕様からが **_ _restrict** C++ または C プログラムで使用できます。

- ときに **_ _restrict**が使用すると、コンパイラは伝達されません変数の非エイリアスのプロパティ。 つまりを割り当てた場合、 **_ _restrict**変数以外に **_ _restrict**変数コンパイラも、-_ _restrict 以外には別名を変数。 これは、別の動作、**制限**C99 仕様のキーワード。

一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。

Visual Studio 2015 以降では、 **_ _restrict** C++ 参照で使用できます。

> [!NOTE]
>  持っている変数に対して使用すると、[揮発性](../cpp/volatile-cpp.md)キーワード、**揮発性**が優先されます。

## <a name="example"></a>例

```cpp
// __restrict_keyword.c
// compile with: /LD
// In the following function, declare a and b as disjoint arrays
// but do not have same assurance for c and d.
void sum2(int n, int * __restrict a, int * __restrict b,
          int * c, int * d) {
   int i;
   for (i = 0; i < n; i++) {
      a[i] = b[i] + c[i];
      c[i] = b[i] + d[i];
    }
}

// By marking union members as __restrict, tell compiler that
// only z.x or z.y will be accessed in any given scope.
union z {
   int * __restrict x;
   double * __restrict y;
};
```

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)