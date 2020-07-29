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
ms.openlocfilehash: 6318e6d78f6c4c4bb6827a79d26bca028dfe3f3f
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233744"
---
# <a name="__restrict"></a>__restrict

**__Declspec ( [restrict](../cpp/restrict.md) )** 修飾子と同様に、 **`__restrict`** キーワードは、現在のスコープでシンボルがエイリアス化されていないことを示します。 キーワードは、 **`__restrict`** 修飾子と `__declspec ( restrict )` 次の点で異なります。

- **`__restrict`** キーワードは変数でのみ有効で、 `__declspec ( restrict )` 関数の宣言と定義でのみ有効です。

- **`__restrict`** は C99 仕様のと似 **`restrict`** ていますが、 **`__restrict`** C++ または C プログラムで使用できます。

- を使用した場合 **`__restrict`** 、コンパイラは変数のエイリアスなしのプロパティを伝達しません。 つまり、変数を非変数に割り当てた場合で **`__restrict`** **`__restrict`** も、コンパイラは非 __restrict 変数に別名を付けることができます。 これは、C99 仕様のキーワードの動作とは異なり **`restrict`** ます。

一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。

以前のバージョンとの互換性 **_restrict**を維持するために、 **`__restrict`** コンパイラオプションの [ [ \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、_restrict はのシノニムになります。

Visual Studio 2015 以降では、を **`__restrict`** C++ 参照で使用できます。

> [!NOTE]
> [Volatile](../cpp/volatile-cpp.md)キーワードも含む変数で使用すると、 **`volatile`** が優先されます。

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
