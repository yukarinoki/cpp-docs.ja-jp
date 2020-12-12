---
description: 詳細については、「コンパイラエラー C3866」を参照してください。
title: コンパイラ エラー C3866
ms.date: 11/04/2016
f1_keywords:
- C3866
helpviewer_keywords:
- C3866
ms.assetid: 685870af-2440-4cdf-a6cb-284a5b96ef9d
ms.openlocfilehash: fceb8ed41a3cbfc287f4c1115cd0502ce8506925
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222867"
---
# <a name="compiler-error-c3866"></a>コンパイラ エラー C3866

関数呼び出しに引数リストがありません

非静的メンバー関数内で、デストラクターまたはファイナライザーの呼び出しに引数リストがありませんでした。

次の例では、C3866 が生成されます。

```cpp
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
