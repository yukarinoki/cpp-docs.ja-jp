---
description: 詳細については、「コンパイラエラー C2587」を参照してください。
title: コンパイラ エラー C2587
ms.date: 11/04/2016
f1_keywords:
- C2587
helpviewer_keywords:
- C2587
ms.assetid: 7637a2c7-35d4-4b5a-a8f2-515a7bda98fd
ms.openlocfilehash: a5d447f2e1a08c310fdd5c2d42afef768f191f4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177602"
---
# <a name="compiler-error-c2587"></a>コンパイラ エラー C2587

' identifier ': ローカル変数が既定のパラメーターとして不適切に使用される

ローカル変数は、既定のパラメーターとして使用することはできません。

次の例では、C2587 が生成されます。

```cpp
// C2587.cpp
// compile with: /c
int i;
void func() {
   int j;
   extern void func2( int k = j );  // C2587 -- local variable
   extern void func3( int k = i );   // OK
}
```
