---
title: コンパイラ エラー C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: 4e2816092b3c0c210ae2c544e9bf9a823a9c5d18
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661137"
---
# <a name="compiler-error-c2657"></a>コンパイラ エラー C2657

' クラス:: *' のステートメントの先頭にある (を忘れました型を指定するか)。

メンバーへのポインターの識別子を持つ行が開始しました。

このエラーは、メンバーへポインターの宣言で型指定子がありませんが発生することができます。

次の例では、C2657 が生成されます。

```
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```