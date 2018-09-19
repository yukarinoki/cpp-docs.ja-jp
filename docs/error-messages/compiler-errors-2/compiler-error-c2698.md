---
title: コンパイラ エラー C2698 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2698
dev_langs:
- C++
helpviewer_keywords:
- C2698
ms.assetid: 3ebfe395-c20b-4c56-9980-ca9ed8653382
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c7ca3e7568640aabd2b7960d97ea94a11a1d5d59
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118922"
---
# <a name="compiler-error-c2698"></a>コンパイラ エラー C2698

使用して、宣言には、' 1' の宣言は、既存の using 宣言用と共存できません ' 2' の宣言

作成したら、[宣言を使用して](../../cpp/using-declaration.md)すべてを使用して、データ メンバー関数のみをオーバー ロードできるよう、同じ名前を使用して、同じスコープ内宣言は許可されませんが。

次の例では、C2698 が生成されます。

```
// C2698.cpp
struct A {
   int x;
};

struct B {
   int x;
};

struct C : A, B {
   using A::x;
   using B::x;   // C2698
}
```