---
title: コンパイラの警告 (レベル 1) C4288
ms.date: 11/04/2016
f1_keywords:
- C4288
helpviewer_keywords:
- C4288
ms.assetid: 6aaeb139-90cd-457a-9d37-65687042736f
ms.openlocfilehash: d8769f5663ca0bde9048e52d4579012dfccab0a1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532029"
---
# <a name="compiler-warning-level-1-c4288"></a>コンパイラの警告 (レベル 1) C4288

使用される標準の拡張機能: 'var': は、for ループ スコープの外側のループで宣言したループ コントロール変数が使用されます。外側のスコープの宣言と競合します。

コンパイルするときに[/Ze](../../build/reference/za-ze-disable-language-extensions.md)と **/Zc:forscope-** で宣言された変数を**の**後ループが使用された、[の](../../cpp/for-statement-cpp.md)-スコープをループします。 C++ 言語への Microsoft 拡張機能により、この変数のスコープ内に存続して、C4288 は、変数の最初の宣言が使用されないことを通知します。

参照してください[/Zc:forScope](../../build/reference/zc-forscope-force-conformance-in-for-loop-scope.md)で Microsoft の拡張機能を指定する方法については**の**/ze オプションでループします。

次の例では、C4288 が生成されます。

```
// C4288.cpp
// compile with: /W1 /c /Zc:forScope-
int main() {
   int i = 0;    // not used in this program
   for (int i = 0 ; ; ) ;
   i++;   // C4288 using for-loop declaration of i
}
```