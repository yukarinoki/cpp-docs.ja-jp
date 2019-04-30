---
title: コンパイラ エラー C2283
ms.date: 11/04/2016
f1_keywords:
- C2283
helpviewer_keywords:
- C2283
ms.assetid: 8a5b3175-b480-4598-a1f7-0b50504c5caa
ms.openlocfilehash: 1113236680241a80c462e382c8c9c7de342b5463
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388749"
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