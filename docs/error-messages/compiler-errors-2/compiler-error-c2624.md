---
title: コンパイラ エラー C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 407629ad2eecd0d3ca6081fefa59ddd60702f913
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456720"
---
# <a name="compiler-error-c2624"></a>コンパイラ エラー C2624

ローカル クラスを使用して 'extern' 変数を宣言することはできません。

ローカル クラスまたは構造体宣言には使用できません`extern`変数。

次の例では、C2624 が生成されます。

```
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```