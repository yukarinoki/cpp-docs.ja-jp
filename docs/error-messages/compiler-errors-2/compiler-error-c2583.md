---
title: コンパイラ エラー C2583
ms.date: 11/04/2016
f1_keywords:
- C2583
helpviewer_keywords:
- C2583
ms.assetid: b1c952dc-872c-47e4-9fc8-4dd72bcee6f9
ms.openlocfilehash: b78b9dd69b701e1a66646234d4603973657e90c6
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62366395"
---
# <a name="compiler-error-c2583"></a>コンパイラ エラー C2583

'identifier': ' const または volatile' 'this' ポインターは、コンス トラクター/デストラクターには

コンス トラクターまたはデストラクターが宣言されている`const`または`volatile`します。 これは認められていません。

次の例では、C2583 が生成されます。

```
// C2583.cpp
// compile with: /c
class A {
public:
   int i;
   A() const;   // C2583

   // try the following line instead
   // A();
};
```