---
title: コンパイラ エラー C2267
ms.date: 11/04/2016
f1_keywords:
- C2267
helpviewer_keywords:
- C2267
ms.assetid: ea63bebb-6208-4367-8440-39be07f9c360
ms.openlocfilehash: 5ff8b0bee1f79d9534841e4368fd5a5249cbb413
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534850"
---
# <a name="compiler-error-c2267"></a>コンパイラ エラー C2267

'function': ブロック スコープを持つ静的関数は無効です

ローカル関数が宣言されている`static`します。 静的関数は、グローバル スコープを設定する必要があります。

次の例では、C2267 が生成されます。

```
// C2267.cpp
static int func2();   // OK
int main() {
    static int func1();   // C2267
}
```