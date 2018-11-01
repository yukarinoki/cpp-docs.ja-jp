---
title: コンパイラ エラー C2459
ms.date: 11/04/2016
f1_keywords:
- C2459
helpviewer_keywords:
- C2459
ms.assetid: 81e29f4c-5b60-40fb-9557-1cdc630d77e8
ms.openlocfilehash: d2e8b375fd1219b11b3a543bf3a565ddee00ccf2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502064"
---
# <a name="compiler-error-c2459"></a>コンパイラ エラー C2459

'identifier': 定義されています。匿名のメンバーとして追加することはできません。

クラス、構造体または共用体は、無名共用体のメンバーでは独自のスコープで再定義します。

次の例では、C2459 が生成されます。

```
// C2459.cpp
// compile with: /c
class C {
   union { int C; };   // C2459
   union { int D; };
};
```