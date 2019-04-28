---
title: コンパイラ エラー C2164
ms.date: 11/04/2016
f1_keywords:
- C2164
helpviewer_keywords:
- C2164
ms.assetid: 55df5024-68a8-45a8-ae6c-e6dba35318a2
ms.openlocfilehash: 3b1c7a94dfca1c2767e14f96204ecda670c8a586
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174823"
---
# <a name="compiler-error-c2164"></a>コンパイラ エラー C2164

'function': 組み込み関数が宣言されていません

`intrinsic`プラグマが宣言されていない関数を使用して (でのみ発生します **/Oi**)。 または、そのヘッダー ファイルを含めずに使用されたコンパイラ組み込み関数のいずれか。

次の例では、C2164 が生成されます。

```
// C2164.c
// compile with: /c
// processor: x86
// Uncomment the following line to resolve.
// #include "xmmintrin.h"
void b(float *p) {
   _mm_load_ss(p);   // C2164
}
```