---
title: コンパイラ エラー C2197
ms.date: 11/04/2016
f1_keywords:
- C2197
helpviewer_keywords:
- C2197
ms.assetid: 6dd5a6ec-bc80-41b9-a4ac-46f80eaca42d
ms.openlocfilehash: 8999edcf37277e2e05a92a6601d60d34a675719c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50527401"
---
# <a name="compiler-error-c2197"></a>コンパイラ エラー C2197

'function': 呼び出しに対する引数が多すぎます

コンパイラで検出された関数を呼び出すためのパラメーターが多すぎるか、または関数の宣言が正しくありません。

次の例では C2197 が生成されます。

```
// C2197.c
// compile with: /Za /c
void func( int );
int main() {
   func( 1, 2 );   // C2197 two actual parameters
   func( 2 );   // OK
}
```