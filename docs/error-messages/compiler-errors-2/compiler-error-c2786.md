---
title: コンパイラ エラー C2786
ms.date: 11/04/2016
f1_keywords:
- C2786
helpviewer_keywords:
- C2786
ms.assetid: 6676d8c0-86dd-4a39-bdda-b75a35f4d137
ms.openlocfilehash: b03155ad1a209ae59327dd31d432f5623f380ac9
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62265998"
---
# <a name="compiler-error-c2786"></a>コンパイラ エラー C2786

'type': _ _uuidof の無効なオペランドです

[_ _Uuidof](../../cpp/uuidof-operator.md)操作はユーザー定義型、またはユーザー定義型のオブジェクトにアタッチされている GUID を使用します。  以下の原因が考えられます。

1. 引数は、ユーザー定義型ではありません。

1. `__uuidof` 引数から GUID を抽出することはできません。

次の例では、C2786 が生成されます。

```
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