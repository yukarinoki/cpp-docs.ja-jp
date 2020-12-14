---
description: 詳細については、「コンパイラエラー C3244」を参照してください。
title: コンパイラ エラー C3244
ms.date: 11/04/2016
f1_keywords:
- C3244
helpviewer_keywords:
- C3244
ms.assetid: dae6c49b-5212-4206-8f61-d4010c0b9969
ms.openlocfilehash: 2c74efd321d87d6451d7949c72f1f50ebb6dface
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307223"
---
# <a name="compiler-error-c3244"></a>コンパイラ エラー C3244

'method': このメソッドは 'interface' によって ('interface' ではなく) 導入されました

指定されたインターフェイスにはなく、別の基底クラスにあるメンバーを [明示的にオーバーライド](../../cpp/explicit-overrides-cpp.md) しようとしました。

次の例では C3244 が生成されます。

```cpp
// C3244.cpp
#pragma warning(disable:4199)

__interface IX15A {
   void f();
};

__interface IX15B {
   void g();
};

class CX15 : public IX15A, public IX15B {
public:
   void IX15A::f();
   void IX15B::g();
};

void CX15::IX15A::g()   // C3244 occurs here
{
}
```
