---
title: コンパイラの警告 (レベル 1) C4319
ms.date: 1/18/2018
f1_keywords:
- C4319
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
ms.openlocfilehash: 20b268bacd6e7e259e9b4fa1c9e98fa6fd353718
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62385473"
---
# <a name="compiler-warning-level-1-c4319"></a>コンパイラの警告 (レベル 1) C4319

> '~': ゼロ拡張'*type1*'to'*type2*' より大きいサイズの

結果、 **~** より大きい型に変換された場合 (ビットごとの補数) 演算子が符号なしとゼロ拡張です。

## <a name="example"></a>例

次の例では、`~(a - 1)`が 32 ビットの unsigned long 式として評価され、ゼロ拡張によって 64 ビットに変換されます。 これは、予期しない操作結果になる可能性があります。

```cpp
// C4319.cpp
// compile with: cl /W4 C4319.cpp
int main() {
   unsigned long a = 0;
   unsigned long long q = 42;
   q = q & ~(a - 1);    // C4319 expected
}
```
