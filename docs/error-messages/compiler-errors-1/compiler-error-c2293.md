---
title: コンパイラ エラー C2293
ms.date: 11/04/2016
f1_keywords:
- C2293
helpviewer_keywords:
- C2293
ms.assetid: 17e7b4e2-368b-4dd7-a01b-d82be60f8e56
ms.openlocfilehash: 8073e952e8248367c444415cfb182743247dc6fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50570639"
---
# <a name="compiler-error-c2293"></a>コンパイラ エラー C2293

'identifier': メンバー変数を __based の指定子にできません。

`__based` 修飾子に対する指定子は、メンバーではないポインターでなければなりません。

次の例では C2293 が生成されます。

```
// C2293.cpp
// compile with: /c
class A {
   static int *i;
   void __based(i) *bp;   // C2293
   void *bp2;   // OK
};
```