---
description: 詳細については、「コンパイラエラー C3848」を参照してください。
title: コンパイラ エラー C3848
ms.date: 11/04/2016
f1_keywords:
- C3848
helpviewer_keywords:
- C3848
ms.assetid: 32d3ccef-01ec-4f8b-bbff-fb9b1a76b4c4
ms.openlocfilehash: 8bd81f59927dd1b34c23148dd1e9bd69ec715609
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97255380"
---
# <a name="compiler-error-c3848"></a>コンパイラ エラー C3848

型 ' type ' を持つ式では、' function ' を呼び出すために const volatile 修飾子が失われます

Const volatile 型が指定された変数は、同じまたはそれ以上の const volatile 修飾子で定義されたメンバー関数のみを呼び出すことができます。

次のサンプルでは、C3848 が生成されます。

```cpp
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
