---
description: 詳細については、「コンパイラエラー C2464」を参照してください。
title: コンパイラ エラー C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: 2e30166529616809478927dbfe6ff1f1efb3002a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341842"
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
