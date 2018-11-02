---
title: コンパイラ エラー C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597276"
---
# <a name="compiler-error-c2055"></a>コンパイラ エラー C2055

型リストではなく、仮パラメーター リストが必要です。

関数定義には、仮パラメーター リストではなく、パラメーターの型リストが含まれています。 ANSI C には、void または省略記号でない限り、名前を指定する正式なパラメーターが必要です。 (`...`)。

次の例では、C2055 が生成されます。

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```