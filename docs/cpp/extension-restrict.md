---
title: __restrict
ms.date: 10/10/2018
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.assetid: 2d151b4d-f930-49df-bd16-d8757ec7fa83
ms.openlocfilehash: 27ac76251456d9a0bf5908ad6d1fc2bee7534e9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81360812"
---
# <a name="__restrict"></a>__restrict

__declspec **( [restrict](../cpp/restrict.md) )** 修飾子と同様に **、__restrict**キーワードは、シンボルが現在のスコープ内でエイリアス化されないことを示します。 **__restrict**キーワードは、修飾子と`__declspec ( restrict )`は次の点で異なります。

- **__restrict**キーワードは変数でのみ有効で`__declspec ( restrict )`、関数の宣言と定義でのみ有効です。

- **__restrict**は C99 仕様からの**制限**に似ていますが **、__restrict**は C++ または C プログラムで使用できます。

- **__restrict**使用すると、コンパイラは変数の no-alias プロパティを反映しません。 つまり、__restrict**以外の変数**に **__restrict**変数を割り当てた場合でも、コンパイラは__restrict以外の変数にエイリアスを設定できます。 これは、**制限キーワードの**C99 仕様からの動作とは異なります。

一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。

以前のバージョンとの互換性のために **、_restrict**コンパイラオプション[/Za\(無効化言語拡張) が](../build/reference/za-ze-disable-language-extensions.md)指定されていない限り **、__restrict**の同義語です。

Visual Studio 2015 以降では **、__restrict** C++ 参照で使用できます。

> [!NOTE]
> [volatile](../cpp/volatile-cpp.md)キーワードも持つ変数で使用すると **、volatile**が優先されます。

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

[Keywords](../cpp/keywords-cpp.md)
