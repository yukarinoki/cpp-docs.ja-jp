---
title: コンパイラの警告 (レベル 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 414388fc1b9c6a7425d45e2ba92546960cadf404
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199616"
---
# <a name="compiler-warning-level-1-c4630"></a>コンパイラの警告 (レベル 1) C4630

' symbol ': ' extern ' ストレージクラス指定子がメンバー定義で無効です。

データメンバーまたはメンバー関数は、`extern`として定義されます。 オブジェクト全体を使用できますが、メンバーを外部にすることはできません。 コンパイラは `extern` キーワードを無視します。 次の例では、C4630 が生成されます。

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
