---
description: '詳細情報: コンパイラの警告 (レベル 1) C4090'
title: コンパイラの警告 (レベル 1) C4090
ms.date: 11/04/2016
f1_keywords:
- C4090
helpviewer_keywords:
- C4090
ms.assetid: baad469d-23d4-45aa-ad9c-305b32d61e9a
ms.openlocfilehash: c096a32e5aa0d632d43d9990f3256c3f865bf796
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278104"
---
# <a name="compiler-warning-level-1-c4090"></a>コンパイラの警告 (レベル 1) C4090

' operation ': 異なる ' modifier ' 修飾子です

操作で使用される変数は、コンパイラによって検出されることなく変更されないように、指定された修飾子を使用して定義されます。 式は、変更せずにコンパイルされます。

この警告は、または項目へのポインター **`const`** **`volatile`** が、またはを指すように宣言されていないポインターに割り当てられている場合に発生することがあり **`const`** **`volatile`** ます。

この警告は C プログラムに対して発行されます。 C++ プログラムでは、コンパイラがエラー [C2440](../../error-messages/compiler-errors-1/compiler-error-c2440.md)を発行します。

次の例では、C4090 が生成されます。

```c
// C4090.c
// compile with: /W1
int *volatile *p;
int *const *q;
int **r;

int main() {
   p = q;   // C4090
   p = r;
   q = p;   // C4090
   q = r;
   r = p;   // C4090
   r = q;   // C4090
}
```
