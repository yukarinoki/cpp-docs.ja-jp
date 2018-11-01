---
title: コンパイラ エラー C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 88a55a469fb8bc08d2ae73209c2e98a99dbc1df0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482019"
---
# <a name="compiler-error-c2523"></a>コンパイラ エラー C2523

' クラス:: ~ identifier': デストラクターまたはファイナライザーのタグが一致しません

デストラクターの名前は、クラス名の前にチルダである必要があります (`~`)。 コンス トラクターとデストラクターは、クラスと同じ名前を持つメンバーのみです。

次の例では、C2523 が生成されます。

```
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```