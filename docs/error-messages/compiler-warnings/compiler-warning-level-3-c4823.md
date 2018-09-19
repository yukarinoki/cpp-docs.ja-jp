---
title: コンパイラの警告 (レベル 3) C4823 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4823
dev_langs:
- C++
helpviewer_keywords:
- C4823
ms.assetid: 8a77560d-dcea-4cae-aebb-8ebf1b4cef85
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 4c3a6f24a32267f221dbc37e242bae48c0056af5
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46044653"
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
