---
title: コンパイラ エラー C2571 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 30cc078251d0511da77e08690db275a788973ffb
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067936"
---
# <a name="compiler-error-c2571"></a>コンパイラ エラー C2571

'function': 仮想関数は、共用体 'union' にすることはできません

仮想関数を持つ共用体が宣言されています。 クラスまたは構造体でのみ仮想関数を宣言することができます。  考えられる解決策:

1. クラスまたは構造体、共用体に変更します。

1. 非仮想関数を作成します。

次の例では、C2571 が生成されます。

```
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```