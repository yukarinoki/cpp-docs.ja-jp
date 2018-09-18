---
title: コンパイラ エラー C2258 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2258
dev_langs:
- C++
helpviewer_keywords:
- C2258
ms.assetid: 105eaa87-befb-4ecb-9a3f-e09e14d2f5bf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3c1d055858a4373a322175e0fda7a4c9ad4a2e05
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46022410"
---
# <a name="compiler-error-c2258"></a>コンパイラ エラー C2258

純粋仮想関数の宣言に構文上の誤りがあります、'= 0' でなければなりません。

純粋仮想関数が正しくない構文で宣言されています。

次の例では C2258 が生成されます。

```
// C2258.cpp
// compile with: /c
class A {
public:
   void virtual func1() = 1; // C2258
   void virtual func2() = 0;   // OK
};
```