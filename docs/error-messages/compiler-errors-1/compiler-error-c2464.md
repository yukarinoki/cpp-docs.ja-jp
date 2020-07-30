---
title: コンパイラ エラー C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: b2d2766b11d15bdb666baa207591cc9ff279a280
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225476"
---
# <a name="compiler-error-c2464"></a>コンパイラ エラー C2464

' identifier ': 参照を割り当てるために ' new ' を使用することはできません

演算子で参照識別子が割り当てられました **`new`** 。 参照はメモリオブジェクトではないため、 **`new`** ポインターを返すことはできません。 参照を宣言するには、標準変数宣言の構文を使用します。

次の例では、C2464 が生成されます。

```cpp
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```
