---
title: コンパイラ エラー C2381
ms.date: 11/04/2016
f1_keywords:
- C2381
helpviewer_keywords:
- C2381
ms.assetid: cc765f67-64ac-406f-93ef-ae7d548d58d7
ms.openlocfilehash: b29f7dac6c6d71e12eb0f003cdfc151dd2c349a7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50663190"
---
# <a name="compiler-error-c2381"></a>コンパイラ エラー C2381

'function': 再定義されています。__declspec(noreturn) とは異なる

関数が宣言され、その定義が使用されますが、定義、 [noreturn](../../cpp/noreturn.md) `__declspec`修飾子。 使用`noreturn`構成関数の再定義; 宣言と定義の使用に同意する必要があります。`noreturn`します。

次の例では、C2381 が生成されます。

```
// C2381.cpp
// compile with: /c
void f1();
void __declspec(noreturn) f1() {}   // C2381
void __declspec(noreturn) f2() {}   // OK
```