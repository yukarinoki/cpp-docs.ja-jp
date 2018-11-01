---
title: コンパイラ エラー C2648
ms.date: 11/04/2016
f1_keywords:
- C2648
helpviewer_keywords:
- C2648
ms.assetid: ce338337-9154-4f85-bb61-b05fdbfad75d
ms.openlocfilehash: fc563c6e85555b113734ec93fc545bb505bd3f38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50610186"
---
# <a name="compiler-error-c2648"></a>コンパイラ エラー C2648

'identifier': 既定のパラメーターには、静的メンバーが必要ですメンバーの使用。

非静的メンバーは、既定のパラメーターとして使用されます。

次の例では、C2648 が生成されます。

```
// C2648.cpp
// compile with: /c
class C {
public:
   int i;
   static int j;
   void func1( int i = i );  // C2648  i is not static
   void func2( int i = j );  // OK
};
```