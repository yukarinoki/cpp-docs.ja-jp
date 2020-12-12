---
description: 詳細については、「コンパイラエラー C2213」を参照してください。
title: コンパイラ エラー C2213
ms.date: 11/04/2016
f1_keywords:
- C2213
helpviewer_keywords:
- C2213
ms.assetid: ff012278-7f3b-4d49-aaed-2349756f6225
ms.openlocfilehash: aa9274f77c2416af286c306f2e6302b5f416a24b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245591"
---
# <a name="compiler-error-c2213"></a>コンパイラ エラー C2213

' modifier ': __based の引数が無効です

変更する引数 **`__based`** が無効です。

次の例では、C2213 が生成されます。

```cpp
// C2213.cpp
// compile with: /c
int i;
int *j;
char __based(i) *p;   // C2213
char __based(j) *p2;   // OK
```
