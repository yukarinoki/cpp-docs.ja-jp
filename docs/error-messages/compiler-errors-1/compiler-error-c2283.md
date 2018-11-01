---
title: コンパイラ エラー C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 1113236680241a80c462e382c8c9c7de342b5463
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50629997"
---
# <a name="compiler-error-c2283"></a>コンパイラ エラー C2283

'identifier' : 名前指定されていない struct が、純粋関数または抽象オーバーライド関数として指定されています

名前が指定されていないクラスまたは構造体のメンバー関数が、純粋指定子で宣言されていますが、これは許可されません。

次の例では C2283 が生成されます。

```
// C2283.cpp
// compile with: /c
struct {
   virtual void func() = 0;   // C2283
};
struct T {
   virtual void func() = 0;   // OK
};
```