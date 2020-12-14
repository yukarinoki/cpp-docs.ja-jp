---
description: 詳細については、「コンパイラエラー C3852」を参照してください。
title: コンパイラ エラー C3852
ms.date: 11/04/2016
f1_keywords:
- C3852
helpviewer_keywords:
- C3852
ms.assetid: 194e5c5e-0dfb-414e-86db-791c11eb610c
ms.openlocfilehash: f5bfeb5507943dc4f860b81912bfb6880621f290
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255237"
---
# <a name="compiler-error-c3852"></a>コンパイラ エラー C3852

' member ' は型 ' type ' を持っています: 集計初期化はこのメンバーを初期化できませんでした

集計の初期化で既定の初期化を受け取ることができないデータメンバーに、集計初期化の一部として既定の初期化を割り当てようとしました。

次のサンプルでは、C3852 が生成されます。

```cpp
// C3852.cpp
struct S
{
   short s;
};

struct S1
{
   int i;
   const S s;
};

struct S2
{
   int i;
   char & rc;
};

int main()
{
   S1 s1 = { 1 };   // C3852 const member
   // try the following line instead
   // S1 s1 = { 1, 2 };

   S2 s2 = { 2 };   // C3852 reference member
   // try the following line instead
   // char c = 'a';
   S2 s2 = { 2, c };
}
```
