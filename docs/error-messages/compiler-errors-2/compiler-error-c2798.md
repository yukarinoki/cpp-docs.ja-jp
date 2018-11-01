---
title: コンパイラ エラー C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: f3e8f0ac260e49866d1c654f89d34bf57a8ffbc1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50463058"
---
# <a name="compiler-error-c2798"></a>コンパイラ エラー C2798

'super::member' があいまいです。

複数の継承構造で参照したメンバーを含めることが[super](../../cpp/super.md)します。 いずれかでエラーを修正する可能性があります。

- D. の継承リストから B1 または B2 を削除します。

- B1 または B2 のデータ メンバーの名前を変更します。

次の例では、C2798 が生成されます。

```
// C2798.cpp
struct B1 {
   int i;
};

struct B2 {
   int i;
};

struct D : B1, B2 {
   void g() {
      __super::i = 4; // C2798
   }
};
```