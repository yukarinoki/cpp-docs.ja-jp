---
title: コンパイラ エラー C2450 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2450
dev_langs:
- C++
helpviewer_keywords:
- C2450
ms.assetid: 929f1c06-8774-468b-be2a-f428757875a2
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7402e538da4b538792a21d87208c954d1ce31777
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46082529"
---
# <a name="compiler-error-c2450"></a>コンパイラ エラー C2450

型 'type' の switch 式は無効です。

`switch`式に無効な型に評価されます。 整数型またはクラス型に評価される必要がありますが、整数型への明確な変換を持つ。 場合に、ユーザー定義型に評価されると、変換演算子を指定する必要があります。

次の例では、C2450 が生成されます。

```
// C2450.cpp
class X {
public:
   int i;
} x;

class Y {
public:
   int i;
   operator int() { return i; }   // conversion operator
} y;

int main() {
   int j = 1;
   switch ( x ) {   // C2450, x is not type int
   // try the following line instead
   // switch ( y ) {
      default:  ;
   }
}
```