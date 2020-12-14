---
description: 詳細については、「コンパイラエラー C2438」を参照してください。
title: コンパイラ エラー C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: 1400ee013e5d507f7fdfe288b97db10ec8216085
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97189887"
---
# <a name="compiler-error-c2438"></a>コンパイラ エラー C2438

' identifier ': コンストラクターを使用して静的クラスデータを初期化できません

コンストラクターは、クラスの静的メンバーを初期化するために使用されます。 静的メンバーは、クラス宣言の外側にある定義で初期化する必要があります。

次の例では、C2438 が生成されます。

```cpp
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
