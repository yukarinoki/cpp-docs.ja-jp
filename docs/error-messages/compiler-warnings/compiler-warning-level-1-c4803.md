---
title: コンパイラの警告 (レベル 1) C4803 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4ea3eba61df387364b5103de19a28d88fe6e52a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024828"
---
# <a name="compiler-warning-level-1-c4803"></a>コンパイラの警告 (レベル 1) C4803

'method': raise メソッドが、イベントと異なるストレージ クラス 'event'

イベントのメソッド、イベントの宣言と同じストレージ クラスが必要です。 コンパイラは、ストレージ クラスが同じになるように、イベントのメソッドを調整します。

この警告は、インターフェイスからイベントを実装するクラスがある場合に発生することができます。 コンパイラが、インターフェイス内でのイベントに raise メソッドを暗黙的に生成しません。 クラスでそのインターフェイスを実装するコンパイラは暗黙的に raise メソッドを生成し、そのメソッドがそのため、仮想されませんが、警告します。 イベントの詳細については、次を参照してください。[イベント](../../windows/event-cpp-component-extensions.md)します。

参照してください[警告](../../preprocessor/warning.md)プラグマについては、警告をオフにする方法。

## <a name="example"></a>例

次の例では、C4803 が生成されます。

```
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
