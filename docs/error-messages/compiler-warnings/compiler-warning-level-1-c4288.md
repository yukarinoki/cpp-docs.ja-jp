---
title: コンパイラの警告 (レベル 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: a732614ac5d71168ece8ada8e468afa5ba54c1f9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220081"
---
# <a name="compiler-warning-level-1-c4288"></a>コンパイラの警告 (レベル 1) C4288

> 非標準の拡張が使用されています: ' var ': for ループで宣言されたループコントロール変数が for ループスコープの外側で使用されています。外側のスコープの宣言と競合します。

[`/Ze`](../../build/reference/za-ze-disable-language-extensions.md)と **/zc: forscope-** を使用してコンパイルするときに、ループで宣言された変数 **`for`** が[for](../../cpp/for-statement-cpp.md)ループスコープの後に使用されました。 C++ 言語の Microsoft 拡張機能を使用すると、この変数をスコープ内に保持でき、C4288 は変数の最初の宣言が使用されないことを通知します。

[`/Zc:forScope`](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)/Ze で Microsoft 拡張機能をループで指定する方法については、「」を参照してください。 **`for`**

次の例では、C4288 が生成されます。

```cpp
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```
