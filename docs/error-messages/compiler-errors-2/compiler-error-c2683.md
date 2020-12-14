---
description: 詳細については、「コンパイラエラー C2683」を参照してください。
title: コンパイラエラー C2683
ms.date: 11/04/2016
f1_keywords:
- C2683
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
ms.openlocfilehash: 9cb13204163370ea529c88cc5648a25a4e520370
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220774"
---
# <a name="compiler-error-c2683"></a>コンパイラエラー C2683

' cast ': ' type ' はポリモーフィックな型ではありません

[Dynamic_cast](../../cpp/dynamic-cast-operator.md)を使用して、非ポリモーフィッククラス (仮想関数を持たないクラス) から変換することはできません。

[Static_cast](../../cpp/static-cast-operator.md)を使用すると、非ポリモーフィック型の変換を実行できます。 ただし、で **`static_cast`** は、実行時チェックは実行されません。

次の例では、C2683 が生成されます。

```cpp
// C2683.cpp
// compile with: /c
class B { };
class D : public B { };

void f(B* pb) {
   D* pd1 = dynamic_cast<D*>(pb);  // C2683
   D* pd1 = static_cast<D*>(pb);   // OK
}
```
