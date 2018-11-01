---
title: コンパイラ エラー C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: 56c4df338feb2c0f406835c1ef2ffeeb7caf8bca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582707"
---
# <a name="compiler-error-c2256"></a>コンパイラ エラー C2256

'function' で friend 指定子の不正な使用

としてデストラクターまたはコンス トラクターを指定することはできません、[フレンド](../../cpp/friend-cpp.md)します。

次の例では、C2256 が生成されます。

```
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```