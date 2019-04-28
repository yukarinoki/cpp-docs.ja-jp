---
title: コンパイラ エラー C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: 98014fec77ce47fa4c484645f401e615f1470e2f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62302301"
---
# <a name="compiler-error-c3866"></a>コンパイラ エラー C3866

関数呼び出しに引数リストがありません。

非静的メンバー関数の内部デストラクターまたはファイナライザーの呼び出しは、引数リストがありませんでした。

次の例では、C3866 が生成されます。

```
// C3866.cpp
// compile with: /c
class C {
   ~C();
   void f() {
      this->~C;   // C3866
      this->~C();   // OK
   }
};
```