---
title: コンパイラ エラー C2528
ms.date: 11/04/2016
f1_keywords:
- C2528
helpviewer_keywords:
- C2528
ms.assetid: 2ea9d583-67a8-4b16-b35f-a50eeffc03c4
ms.openlocfilehash: 890dae7aa34103bde0168f1933bb42343d84100b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601748"
---
# <a name="compiler-error-c2528"></a>コンパイラ エラー C2528

'name': 参照へのポインターは無効です

参照へのポインターを宣言することはできません。 ポインターを宣言する前に、変数を逆参照します。

次の例では、C2528 が生成されます。

```
// C2528.cpp
int i;
int &ir = i;
int & (*irptr) = ir;    // C2528
```