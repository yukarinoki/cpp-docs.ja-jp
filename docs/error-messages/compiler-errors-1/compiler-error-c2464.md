---
title: コンパイラ エラー C2464
ms.date: 11/04/2016
f1_keywords:
- C2464
helpviewer_keywords:
- C2464
ms.assetid: ace953d6-b414-49ee-bfef-90578a8da00c
ms.openlocfilehash: a00ac997f73175eeab08a0132128e48e8fc58feb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50498190"
---
# <a name="compiler-error-c2464"></a>コンパイラ エラー C2464

'identifier': 'new' の参照の割り当てに使用できません

参照識別子で割り当てられた、`new`演算子。 参照がそのため、メモリ オブジェクトされてない`new`それらへのポインターを返すことはできません。 標準の変数宣言の構文を使用して、参照を宣言します。

次の例では、C2464 が生成されます。

```
// C2464.cpp
int main() {
   new ( int& ir );   // C2464
}
```