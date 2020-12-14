---
description: 詳細については、「コンパイラエラー C2332」を参照してください。
title: コンパイラ エラー C2332
ms.date: 11/04/2016
f1_keywords:
- C2332
helpviewer_keywords:
- C2332
ms.assetid: fb05cd68-e271-4bea-9fb7-ef4edb0a26ac
ms.openlocfilehash: 9733e588c3f24d61da154d7cb14a5eeecc30e2c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234918"
---
# <a name="compiler-error-c2332"></a>コンパイラ エラー C2332

' typedef ': タグ名がありません

不完全な型の定義がコンパイラによって検出されました。

次の例では、C2332 が生成されます。

```cpp
// C2332.cpp
// compile with: /c
struct S {
   int i;
};

typedef struct * pS;   // C2332
typedef struct S* pS;   // OK

int get_S_i(pS p) {
   return p->i;
}
```
