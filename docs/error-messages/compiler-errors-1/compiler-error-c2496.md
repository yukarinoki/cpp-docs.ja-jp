---
title: コンパイラ エラー C2496
ms.date: 11/04/2016
f1_keywords:
- C2496
helpviewer_keywords:
- C2496
ms.assetid: 9a25237d-5bbb-4112-98f3-29cd99d3f89f
ms.openlocfilehash: 258012fdefed877558f122790954d830095d5026
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360582"
---
# <a name="compiler-error-c2496"></a>コンパイラ エラー C2496

'identifier': 'selectany' は外部リンケージを持つデータ項目にのみ適用できます

[Selectany](../../cpp/selectany.md)属性は、外部から参照できるグローバル データ項目にのみ適用できます。

次の例では、C2496 が生成されます。

```
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