---
title: コンパイラ エラー C3231 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3231
dev_langs:
- C++
helpviewer_keywords:
- C3231
ms.assetid: fe5dc352-e634-45fa-9534-3da176294c98
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 57727fbd71314201ec76119d37ab9c73b01d471d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097316"
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