---
title: コンパイラ エラー C3210 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3210
dev_langs:
- C++
helpviewer_keywords:
- C3210
ms.assetid: c6e9d309-fabc-4e7d-b526-be20d9fe3f6a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 804586a866f6a4d2c3cf206af14e0e2f907ed1b6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037113"
---
# <a name="compiler-error-c3210"></a>コンパイラ エラー C3210

'type': アクセス宣言は、基底クラスのメンバーにのみ適用できます

A[宣言を使用して](../../cpp/using-declaration.md)正しく指定されていません。

## <a name="example"></a>例

次の例では、C3210 が生成されます。

```
// C3210.cpp
// compile with: /c
struct A {
protected:
   int i;
};

struct B {
   using A::i;   // C3210
};

struct C : public A {
   using A::i;   // OK
};
```