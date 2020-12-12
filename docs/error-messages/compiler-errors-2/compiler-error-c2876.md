---
description: 詳細については、「コンパイラエラー C2876」を参照してください。
title: コンパイラ エラー C2876
ms.date: 11/04/2016
f1_keywords:
- C2876
helpviewer_keywords:
- C2876
ms.assetid: 8b674bf1-f9f4-4a8e-8127-e884c1d1708f
ms.openlocfilehash: 5d83c1dd57c074354d3643452a1a2189bcbd860e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320500"
---
# <a name="compiler-error-c2876"></a>コンパイラ エラー C2876

' class:: symbol ': すべてのオーバーロードにアクセスできるわけではありません

基底クラスの関数のオーバーロードされたすべての形式は、派生クラスからアクセスできる必要があります。

次の例では、C2876 が生成されます。

```cpp
// C2876.cpp
// compile with: /c
class A {
public:
   double a(double);
private:
   int a(int);
};

class B : public A {
   using A::a;   // C2876 one overload is private in base class
};
```
