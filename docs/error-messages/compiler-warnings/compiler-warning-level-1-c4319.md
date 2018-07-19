---
title: コンパイラの警告 (レベル 1) C4319 |Microsoft ドキュメント
ms.custom: ''
ms.date: 1/18/2018
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4319
dev_langs:
- C++
helpviewer_keywords:
- C4319
ms.assetid: 1fac8048-9bd6-4552-a21c-192c67772bb9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c1b5fe896ae7d8f43708b60ee4dda486ef08f428
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/04/2018
ms.locfileid: "33284746"
---
# <a name="compiler-warning-level-1-c4319"></a>コンパイラの警告 (レベル 1) C4319

> '~': ゼロ拡張'*type1*'to'*type2*' より大きいサイズの

結果、 **~** (ビットごとの補数) 演算子、符号なしとゼロ拡張のときより大きい型に変換されます。

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
