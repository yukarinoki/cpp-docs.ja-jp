---
title: コンパイラ エラー C2675
ms.date: 11/04/2016
f1_keywords:
- C2675
helpviewer_keywords:
- C2675
ms.assetid: 4b92a12b-bff8-4dd5-a109-620065fc146c
ms.openlocfilehash: aea79509d0e1ae5c31fcf0cf369c28af39a21154
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50499831"
---
# <a name="compiler-error-c2675"></a>コンパイラ エラー C2675

単項 'operator': 'type' に定義を行いませんこの演算子または適切な型への変換定義済の演算子

C2675 は、単項演算子を使用する場合にも発生することができ、型に定義を行いません、演算子、または適切な型への変換定義済の演算子。 この演算子を使うには、型を指定してこの演算子をオーバーロードするか、この演算子が定義された型への変換を定義する必要があります。

## <a name="example"></a>例

次の例では、C2675 が生成されます。

```
// C2675.cpp
struct C {
   C(){}
} c;

struct D {
   D(){}
   void operator-(){}
} d;

int main() {
   -c;   // C2675
   -d;   // OK
}
```