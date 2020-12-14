---
description: 詳細については、「コンパイラエラー C2798」を参照してください。
title: コンパイラエラー C2798
ms.date: 11/04/2016
f1_keywords:
- C2798
helpviewer_keywords:
- C2798
ms.assetid: fb0cd861-b228-4f81-8090-e28344a727e0
ms.openlocfilehash: d3a78eaf09797d658c64b5659dcd0e05191fab1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297591"
---
# <a name="compiler-error-c2798"></a>コンパイラエラー C2798

' super:: member ' があいまいです

継承された複数の構造体には、 [super](../../cpp/super.md)で参照したメンバーが含まれています。 エラーを修正するには、次のいずれかの方法を使用します。

- D の継承リストから B1 または B2 を削除します。

- B1 または B2 のデータメンバーの名前を変更します。

次の例では、C2798 が生成されます。

```cpp
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
