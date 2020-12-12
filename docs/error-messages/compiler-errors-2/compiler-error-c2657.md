---
description: 詳細については、「コンパイラエラー C2657」を参照してください。
title: コンパイラエラー C2657
ms.date: 11/04/2016
f1_keywords:
- C2657
helpviewer_keywords:
- C2657
ms.assetid: f7cf29a9-684a-4605-9469-ecfee9ba4b03
ms.openlocfilehash: dfec399c4b65615310263aa58db145b87c42594d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286073"
---
# <a name="compiler-error-c2657"></a>コンパイラエラー C2657

ステートメントの先頭に ' class::* ' が見つかりました (型を指定してください)。

行は、メンバーへのポインターの識別子で始まりました。

このエラーは、メンバーへのポインターの宣言で、型指定子が欠落していることが原因で発生する可能性があります。

次の例では、C2657 が生成されます。

```cpp
// C2657.cpp
class C {};
int main() {
   C::* pmc1;        // C2657
   int C::* pmc2;   // OK
}
```
