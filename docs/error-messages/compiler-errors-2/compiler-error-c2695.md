---
title: コンパイラ エラー C2695
ms.date: 11/04/2016
f1_keywords:
- C2695
helpviewer_keywords:
- C2695
ms.assetid: 3f6f2091-c38b-40ea-ab6c-f1846f5702d7
ms.openlocfilehash: 08f74bf635324ed9a05c13ecf532862d58e4f0b1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62368189"
---
# <a name="compiler-error-c2695"></a>コンパイラ エラー C2695

'function1': 'function2' 呼び出し規約のみが異なる仮想関数のオーバーライド

派生クラスでの関数のシグネチャは、基本クラスの関数をオーバーライドし、呼び出し規則を変更ことはできません。

次の例では、C2695 が生成されます。

```
// C2695.cpp
class C {
   virtual void __fastcall func();
};

class D : public C {
   virtual void __clrcall func();   // C2695
};
```