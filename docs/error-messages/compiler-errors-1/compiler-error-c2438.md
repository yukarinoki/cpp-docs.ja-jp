---
title: コンパイラ エラー C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: b2861090b5f7629c7f0cd94ea38a99e888909258
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50630504"
---
# <a name="compiler-error-c2438"></a>コンパイラ エラー C2438

'identifier': コンス トラクターを使用して静的クラスのデータを初期化できません

コンス トラクターを使用して、クラスの静的メンバーを初期化します。 クラス宣言の外側の定義では、静的メンバーを初期化する必要があります。

次の例では、C2438 が生成されます。

```
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```