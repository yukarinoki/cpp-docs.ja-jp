---
description: 詳細については、「コンパイラエラー C2276」を参照してください。
title: コンパイラ エラー C2276
ms.date: 03/25/2021
f1_keywords:
- C2276
helpviewer_keywords:
- C2276
ms.openlocfilehash: 85a83637e12f0900f3a6840841c7a9a8ed50deee
ms.sourcegitcommit: 82a0d23b04d0776c00209d885689cbc5be36d3b9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/31/2021
ms.locfileid: "106099470"
---
# <a name="compiler-error-c2276"></a>コンパイラ エラー C2276

> '*operator*': バインドされたメンバー関数式に対する無効な操作です。

コンパイラにより、メンバーへのポインターの作成に使用された構文に問題が見つかりました。

## <a name="remarks"></a>解説

`C2276`多くの場合、エラーは、クラス型ではなく、メンバーを修飾するためにインスタンス変数を使用してメンバーへのポインターを作成しようとすると発生します。 間違った構文を使用してメンバー関数を呼び出そうとした場合にも、このエラーが発生することがあります。

## <a name="example"></a>例

このサンプルでは、C2276 が発生するいくつかの方法と、それらを修正する方法を示します。

```cpp
// C2276.cpp
class A {
public:
   int func(){return 0;}
} a;

int (*pf)() = &a.func;   // C2276
// pf isn't qualified by the class type, and it 
// tries to take a member address from an instance of A.
// Try the following line instead:
// int (A::*pf)() = &A::func;

class B : public A {
public:
   void mf() {
      auto x = &this -> func;   // C2276
      // try the following line instead
      // auto x = &B::func;
   }
};

int main() {
   A a3;
   auto pmf1 = &a3.func;   // C2276
   // try the following line instead
   // auto pmf1 = &A::func;
}
```
