---
title: コンパイラの警告 (レベル 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 3a533afe141a465fb034ba7d90b22a8206bf0910
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230624"
---
# <a name="compiler-warning-level-1-c4630"></a>コンパイラの警告 (レベル 1) C4630

' symbol ': ' extern ' ストレージクラス指定子がメンバー定義で無効です。

データメンバーまたはメンバー関数は、として定義され **`extern`** ます。 オブジェクト全体を使用できますが、メンバーを外部にすることはできません。 コンパイラはキーワードを無視し **`extern`** ます。 次の例では、C4630 が生成されます。

```cpp
// C4630.cpp
// compile with: /W1 /LD
class A {
   void func();
};

extern void A::func() {   // C4630, remove 'extern' to resolve
}
```
