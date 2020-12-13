---
description: 詳細については、「コンパイラエラー C2556」を参照してください。
title: コンパイラ エラー C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 6c2233e10e763e959511c6b435e0d894e921905a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134486"
---
# <a name="compiler-error-c2556"></a>コンパイラ エラー C2556

' identifier ': オーバーロードされた関数は戻り値の型のみが異なります

オーバーロードされた関数の戻り値の型は異なりますが、同じパラメーターリストが指定されています。 オーバーロードされた各関数には、個別の仮パラメーターリストが必要です。

次の例では、C2556 が生成されます。

```cpp
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```
