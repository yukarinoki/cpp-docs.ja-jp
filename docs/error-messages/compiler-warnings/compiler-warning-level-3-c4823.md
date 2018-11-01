---
title: コンパイラの警告 (レベル 3) C4823
ms.date: 11/04/2016
f1_keywords:
- C4823
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
ms.openlocfilehash: 28d490c341c4d14c2e6c03e13007b5a8be423622
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625911"
---
# <a name="compiler-warning-level-3-c4823"></a>コンパイラの警告 (レベル 3) C4823

'function': を使用して固定ポインターは、アンワインド セマンティクスが有効になっていません。 /EHa を使用してください。

固定を解除するには、ブロック スコープで宣言された固定ポインターが指すマネージ ヒープ上のオブジェクトには、コンパイラは、「装った」は、固定ポインターにポインターを null にするデストラクターを持つ、ローカルのクラスのデストラクターの動作をシミュレートします。 例外をスローした後、デストラクターの呼び出しを有効にする必要がありますを有効にしたオブジェクト アンワインディングを使用して行うことができますが[/EHsc](../../build/reference/eh-exception-handling-model.md)します。

手動でオブジェクトの固定を解除し、警告を無視できます。

## <a name="example"></a>例

次の例では、C4823 が生成されます。

```
// C4823.cpp
// compile with: /clr /W3 /EHa-
using namespace System;

ref struct G {
   int m;
};

void f(G ^ pG) {
   try {
      pin_ptr<int> p = &pG->m;
      // manually unpin, ignore warning
      // p = nullptr;
      throw gcnew Exception;
   }
   catch(Exception ^) {}
}   // C4823 warning

int main() {
   f( gcnew G );
}
```
