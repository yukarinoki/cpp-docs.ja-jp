---
description: 詳細については、「コンパイラエラー C2695」を参照してください。
title: コンパイラエラー C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 6137749725de5c2285cb5defd84fd7c8c0f2e237
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326644"
---
# <a name="compiler-error-c2695"></a>コンパイラエラー C2695

' function1 ': オーバーライドする仮想関数は、呼び出し規約によってのみ ' function2 ' と異なります

派生クラスの関数のシグネチャは、基底クラスの関数をオーバーライドし、呼び出し規約を変更することはできません。

次の例では、C2695 が生成されます。

```cpp
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```
