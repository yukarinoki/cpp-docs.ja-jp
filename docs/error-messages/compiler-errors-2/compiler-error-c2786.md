---
description: 詳細については、「コンパイラエラー C2786」を参照してください。
title: コンパイラエラー C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: 64c794281da775df94187a1e871ab3e48bc35a3c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297864"
---
# <a name="compiler-error-c2786"></a>コンパイラエラー C2786

' type ': __uuidof の無効なオペランドです

[__Uuidof](../../cpp/uuidof-operator.md)演算子は、GUID が割り当てられたユーザー定義型、またはそのようなユーザー定義型のオブジェクトを受け取ります。  次の原因が考えられます。

1. 引数がユーザー定義型ではありません。

1. **`__uuidof`** 引数から GUID を抽出できません。

次の例では、C2786 が生成されます。

```cpp
// C2786.cpp
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};

int main() {
   __uuidof(int);   // C2786
   __uuidof(int *);   // C2786
   __uuidof(A **);   // C2786

   // no error
   __uuidof(A);
   __uuidof(A *);
   __uuidof(A &);
   __uuidof(A[]);

   int i;
   int *pi;
   A **ppa;

   __uuidof(i);      // C2786
   __uuidof(pi);     // C2786
   __uuidof(ppa);    // C2786
}
```
