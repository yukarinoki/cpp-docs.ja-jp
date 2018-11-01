---
title: コンパイラ エラー C2556
ms.date: 11/04/2016
f1_keywords:
- C2556
helpviewer_keywords:
- C2556
ms.assetid: fc4399ad-45b3-49fd-be1f-0b13956a595a
ms.openlocfilehash: 4a2b4dc9dcd71d518845651dee97c566b778eb0a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484150"
---
# <a name="compiler-error-c2556"></a>コンパイラ エラー C2556

'identifier': オーバー ロードされた関数は、戻り値の型のみが異なる

オーバー ロードされた関数では、同じパラメーター リストが異なる戻り値の型があります。 各オーバー ロードされた関数は、個別の仮パラメーター リストにあります。

次の例では、C2556 が生成されます。

```
// C2556.cpp
// compile with: /c
class C {
   int func();
   double func();   // C2556
   int func(int i);   // ok parameter lists differ
};
```