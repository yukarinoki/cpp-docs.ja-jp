---
title: コンパイラの警告 (レベル 1) C4052
ms.date: 11/04/2016
f1_keywords:
- C4052
helpviewer_keywords:
- C4052
ms.assetid: f9955421-16ab-46e5-8f9d-bf1639a519ef
ms.openlocfilehash: c7d2a603b7ec97889b075c7a67e5b8439ad487af
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599629"
---
# <a name="compiler-warning-level-1-c4052"></a>コンパイラの警告 (レベル 1) C4052

関数に対する宣言の 1 つに可変個の引数が含まれていません。

関数の 1 つの宣言に、可変個の引数が含まれません。 これは無視されます。

次の例では C4052 が生成されます。

```
// C4052.c
// compile with: /W4 /c
int f();
int f(int i, ...);   // C4052
```