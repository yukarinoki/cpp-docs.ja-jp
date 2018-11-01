---
title: コンパイラ エラー C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 1d738311ada14999a5345a4e2394631254dda00a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50448323"
---
# <a name="compiler-error-c3848"></a>コンパイラ エラー C3848

型 'type' を含む式は 'function' を呼び出すためにいくつかの const volatile 修飾子が失われる

指定した const volatile 型の変数は、メンバーが const volatile の制限が同じかそれ以上定義されている関数を呼び出すのみできます。

次の例では、C3848 を生成します。

```
// C3848.cpp
void glbFunc1()
{
}

typedef void (* pFunc1)();

struct S3
{
   operator pFunc1() // const
   {
      return &glbFunc1;
   }
};

int main()
{
   const S3 s3;
   s3();   // C3848, uncomment const qualifier
}
```