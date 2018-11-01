---
title: コンパイラの警告 (レベル 1) C4804
ms.date: 11/04/2016
f1_keywords:
- C4804
helpviewer_keywords:
- C4804
ms.assetid: 069e8f44-3ef6-43bb-8524-4116fc6eea83
ms.openlocfilehash: 28b3e49717993a3bf20c8cfec5938d698266c0f9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50476077"
---
# <a name="compiler-warning-level-1-c4804"></a>コンパイラの警告 (レベル 1) C4804

'operation': 操作では、' bool' 型の安全でない使用

この警告を使用したときに、`bool`変数、または予期しない値です。 C4804 が生成された負の値の単項演算子などの演算子を使用する場合など (**-**) または補数演算子 (`~`)。 コンパイラは、式を評価します。

## <a name="example"></a>例

次の例では、C4804 が生成されます。

```
// C4804.cpp
// compile with: /W1

int main()
{
   bool i = true;
   if (-i)   // C4804, remove the '-' to resolve
   {
      i = false;
   }
}
```