---
title: '`__restrict`'
description: Microsoft Visual C++ キーワードについて説明し `__restrict` ます。
ms.date: 11/6/2020
f1_keywords:
- __restrict_cpp
- __restrict
- _restrict
helpviewer_keywords:
- __restrict keyword [C++]
ms.openlocfilehash: f23574f49712928e0095f29a3b88b0c05b185eab
ms.sourcegitcommit: 3f0c1dcdcce25865d1a1022bcc5b9eec79f69025
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2020
ms.locfileid: "94381572"
---
# `__restrict`

**`__declspec` ( [`restrict`](../cpp/restrict.md) )** 修飾子と同様に、 **`__restrict`** キーワード (2 つの先頭のアンダースコア ' _ ') は、現在のスコープでシンボルがエイリアス化されていないことを示します。 キーワードは、 **`__restrict`** 修飾子と `__declspec (restrict)` 次の点で異なります。

- **`__restrict`** キーワードは変数でのみ有効で、 `__declspec (restrict)` 関数の宣言と定義でのみ有効です。

- **`__restrict`** は [`restrict`](../c-language/type-qualifiers.md#restrict) 、C99 で始まる C のと似ていますが、 **`__restrict`** C++ と C プログラムの両方で使用できます。

- を使用した場合 **`__restrict`** 、コンパイラは変数のエイリアスなしのプロパティを反映しません。 つまり、変数を非変数に割り当てた場合で **`__restrict`** **`__restrict`** も、コンパイラは非 __restrict 変数に別名を付けることができます。 これは、C99 C 言語キーワードの動作とは異なり **`restrict`** ます。

一般に、関数全体の動作に影響を与える場合は、キーワードの代わりにを使用し **`__declspec (restrict)`** ます。

以前のバージョンとの互換性のために、 **`_restrict`** **`__restrict`** コンパイラオプションの [ [ `/Za` \( 言語拡張を無効にする](../build/reference/za-ze-disable-language-extensions.md)] が指定されていない場合、はのシノニムになります。

Visual Studio 2015 以降では、を **`__restrict`** C++ 参照で使用できます。

> [!NOTE]
> キーワードも含む変数で使用すると [`volatile`](../cpp/volatile-cpp.md) 、 **`volatile`** が優先されます。

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
