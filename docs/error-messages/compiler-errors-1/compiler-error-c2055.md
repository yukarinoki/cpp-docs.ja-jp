---
title: コンパイラ エラー C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408788"
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