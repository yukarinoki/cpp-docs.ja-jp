---
description: 詳細については、「コンパイラエラー C2496」を参照してください。
title: コンパイラ エラー C2496
ms.date: 11/04/2016
f1_keywords:
- C2496
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
ms.openlocfilehash: da03162e5ba674267df25463a27f08f3f6032e70
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283697"
---
# <a name="compiler-error-c2496"></a>コンパイラ エラー C2496

' identifier ': ' selectany ' は、外部リンケージを持つデータ項目にのみ適用できます

[Selectany](../../cpp/selectany.md)属性は、外部から参照できるグローバルデータ項目にのみ適用できます。

次の例では、C2496 が生成されます。

```cpp
// C2496.cpp
// compile with: /c
__declspec(selectany) int x1 = 1;
const __declspec(selectany) int x2 = 2;   // C2496
static __declspec(selectany) int x6 = 6;   // C2496

extern const __declspec(selectany) int x3 = 3;

__declspec(selectany) int x4;

// dynamic initialization of x5
int f();
__declspec(selectany) int x5 = f();

extern const int x7;
// OK - redeclaration of x7 that is extern
const __declspec(selectany) int x7 = 7;
```
