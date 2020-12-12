---
description: '詳細情報: コンパイラの警告 (レベル 1) C4630'
title: コンパイラの警告 (レベル 1) C4630
ms.date: 11/04/2016
f1_keywords:
- C4630
helpviewer_keywords:
- C4630
ms.assetid: d8926376-7acc-4fc7-8438-6f0de3468870
ms.openlocfilehash: 49a73dcd3ce11fefa1d4275e57ad98092c242d8d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318911"
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
