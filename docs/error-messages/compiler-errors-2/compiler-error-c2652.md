---
title: コンパイラ エラー C2652
ms.date: 11/04/2016
f1_keywords:
- C2652
helpviewer_keywords:
- C2652
ms.assetid: 6e3d1a90-a989-4088-8afd-dc82f6a2d66f
ms.openlocfilehash: 9c9772052b690ad87de1d408c06478d82d48e724
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50464806"
---
# <a name="compiler-error-c2652"></a>コンパイラ エラー C2652

'identifier': コピー コンス トラクター: 最初のパラメーターが 'identifier' を認めない

コピー コンス トラクターの最初のパラメーターは、クラス、構造体または共用体が定義されているのと同じ型です。 最初のパラメーターは、型が型自体への参照を指定できます。

次の例では、C2651 が生成されます。

```
// C2652.cpp
// compile with: /c
class A {
   A( A );   // C2652 takes an A
};
class B {
   B( B& );   // OK, reference to B
};
```