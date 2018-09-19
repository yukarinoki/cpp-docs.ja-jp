---
title: コンパイラ エラー C2683 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c13836c845e1efc33c409939bdbec49b25c84e63
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027596"
---
# <a name="compiler-error-c2683"></a>コンパイラ エラー C2683

'cast': 'type' はポリモーフィックな型ではありません

使用することはできません[dynamic_cast](../../cpp/dynamic-cast-operator.md)から非ポリモーフィックなクラス (仮想関数がないクラス) に変換します。

使用することができます[static_cast](../../cpp/static-cast-operator.md)非ポリモーフィックな型の変換を実行します。 ただし、`static_cast`ランタイム チェックは行われません。

次の例では、C2683 が生成されます。

```
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```