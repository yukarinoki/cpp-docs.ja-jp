---
title: コンパイラ エラー C3231
ms.date: 11/04/2016
f1_keywords:
- C3231
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
ms.openlocfilehash: 653f0b18737f937483f5d3e79cb99c9a55160c19
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50571965"
---
# <a name="compiler-error-c3231"></a>コンパイラ エラー C3231

'arg': テンプレート型引数はジェネリック型パラメーターを使用できません

テンプレートはコンパイル時にインスタンス化されますが、ジェネリックは実行時にインスタンス化されます。 したがって、ジェネリック型が最終的に確定する実行時にテンプレートをインスタンス化することはできないため、テンプレートを呼び出せるジェネリック コードを生成することができません。

次の例では、C3231 が生成されます。

```
// C3231.cpp
// compile with: /clr /LD
template <class T> class A;

generic <class T>
ref class C {
   void f() {
      A<T> a;   // C3231
   }
};
```