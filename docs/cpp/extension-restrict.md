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
ms.openlocfilehash: cb340554bc20516175400c4d14a5d0dba934a313
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80188962"
---
# <a name="__restrict"></a>__restrict

**__Declspec ( [restrict](../cpp/restrict.md) )** 修飾子と同様に、 **__restrict**キーワードは、現在のスコープでシンボルがエイリアス化されていないことを示します。 **__Restrict**キーワードは、次の方法で `__declspec ( restrict )` 修飾子とは異なります。

- **__Restrict**キーワードは変数でのみ有効で、`__declspec ( restrict )` は関数の宣言と定義でのみ有効です。

- **__restrict**は C99 仕様の**制限**に似ていますが、または C C++プログラムでは **__restrict**を使用できます。

- **__Restrict**が使用されている場合、コンパイラは変数のエイリアスなしのプロパティを伝達しません。 つまり、 **__restrict**変数を非 **__restrict**変数に割り当てた場合でも、コンパイラは非 __restrict 変数を別名にすることを許可します。 これは、C99 仕様の**restrict**キーワードの動作とは異なります。

一般に、関数全体の動作に影響を及ぼす場合、キーワードよりも `__declspec ( restrict )` を使用する方が適切です。

以前のバージョンとの互換性のために、コンパイラオプション[/za \(無効になっている言語拡張)](../build/reference/za-ze-disable-language-extensions.md)が指定されていない場合、 **_restrict**は **__restrict**のシノニムになります。

Visual Studio 2015 以降では、 **__restrict**を参照でC++使用できます。

> [!NOTE]
>  [Volatile](../cpp/volatile-cpp.md)キーワードも含む変数で使用すると、 **volatile**が優先されます。

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

## <a name="see-also"></a>参照

[キーワード](../cpp/keywords-cpp.md)
