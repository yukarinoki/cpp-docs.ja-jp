---
title: コンパイラの警告 (レベル 4) C4254 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- c4254
dev_langs:
- C++
helpviewer_keywords:
- C4254
ms.assetid: c7dcef24-d535-4c98-bb41-fc3d2b88fd11
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 039ce69f624fdcdd6beba2d6d262f920b7848687
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46115938"
---
# <a name="compiler-warning-level-4-c4254"></a>コンパイラの警告 (レベル 4) C4254

'operator': 'type1' から 'type2'、データ損失の可能性への変換

サイズの大きなビット フィールドは、小さいビット フィールドに割り当てられました。 データが失われる可能性があります。

既定では、この警告はオフに設定されています。 詳細については、「 [既定で無効になっているコンパイラ警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md) 」を参照してください。

次の例では、C4254 が生成されます。

```
// C4254.cpp
// compile with: /W4
#pragma warning(default: 4254)

struct X {
   int a : 20;
   int b : 12;
};

int main() {
   X *x = new X();
   x->b = 10;
   x->a = 4;
   x->a = x->b;    // OK
   x->b = x->a;    // C4254
};
```