---
description: 詳細については、「コンパイラエラー C2877」を参照してください。
title: コンパイラ エラー C2877
ms.date: 11/04/2016
f1_keywords:
- C2877
helpviewer_keywords:
- C2877
ms.assetid: 0b54837e-fcae-4d90-9658-623250435e24
ms.openlocfilehash: fd5a122cfed34c59e4a597bb6371a026a90c2ebb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320487"
---
# <a name="compiler-error-c2877"></a>コンパイラ エラー C2877

' symbol ' は ' class ' からアクセスできません

基底クラスから派生したすべてのメンバーは、派生クラスでアクセス可能である必要があります。

次の例では、C2877 が生成されます。

```cpp
// C2877.cpp
// compile with: /c
class A {
private:
   int a;
};

class B : public A {
   using A::a;   // C2877
};
```
