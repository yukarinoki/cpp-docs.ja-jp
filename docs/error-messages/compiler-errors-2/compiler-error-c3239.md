---
description: 詳細については、「コンパイラエラー C3239」を参照してください。
title: コンパイラ エラー C3239
ms.date: 11/04/2016
f1_keywords:
- C3239
helpviewer_keywords:
- C3239
ms.assetid: 22a518b7-020f-4f3c-9963-a094667fd1ac
ms.openlocfilehash: ed16767b8076d93176936e53922426d1c87b35da
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307354"
---
# <a name="compiler-error-c3239"></a>コンパイラ エラー C3239

'type': interior およびピン ポインターへのポインターは、共通言語ランタイムによって許可されていません

コンパイラは無効な型を見つけました。

次の例では C3229 が生成されます。

```cpp
// C3239.cpp
// compile with: /clr
int main() {
   interior_ptr<int>* pip0;   // C3239

   // OK
   int * pip1;
   interior_ptr<int> pip2;
   int ** pip;
}
```
