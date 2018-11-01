---
title: コンパイラの警告 (レベル 1) C4817
ms.date: 11/04/2016
f1_keywords:
- C4817
helpviewer_keywords:
- C4817
ms.assetid: a68f5486-6940-4934-9f93-bfd4d71f92a9
ms.openlocfilehash: bb6eb8899efdab3cae39f77079f7eed72344acc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666879"
---
# <a name="compiler-warning-level-1-c4817"></a>コンパイラの警告 (レベル 1) C4817

'member': このメンバーにアクセスするのに '.' が不適切に使用されています。コンパイラは '->' に置き換えられます

間違ったメンバー アクセス演算子が使用されました。

## <a name="example"></a>例

次の例では C4817 が生成されます。

```
// C4817.cpp
// compile with: /clr /W1
using namespace System;
int main() {
   array<Int32> ^ a = gcnew array<Int32>(100);
   Console::WriteLine( a.Length );   // C4817
   Console::WriteLine( a->Length );   // OK
}
```
