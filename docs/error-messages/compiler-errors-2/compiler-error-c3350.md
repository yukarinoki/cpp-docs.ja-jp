---
description: 詳細については、「コンパイラエラー C3350」を参照してください。
title: コンパイラ エラー C3350
ms.date: 11/04/2016
f1_keywords:
- C3350
helpviewer_keywords:
- C3350
ms.assetid: cfbbc338-92b5-4f34-999e-aa2d2376bc70
ms.openlocfilehash: edda71fdf8f1160d17099a7cee228a053ddd881b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326015"
---
# <a name="compiler-error-c3350"></a>コンパイラ エラー C3350

'delegate': delegate コンストラクターには数値の引数が必要です

デリゲートのインスタンスを作成するときは、デリゲート関数含む型のインスタンスと関数の 2 つの引数を渡す必要があります。

次の例では C3350 が生成されます。

```cpp
// C3350.cpp
// compile with: /clr
delegate void SumDelegate();

public ref class X {
public:
   void F() {}
   static void F2() {}
};

int main() {
   X ^ MyX = gcnew X();
   SumDelegate ^ pSD = gcnew SumDelegate();   // C3350
   SumDelegate ^ pSD1 = gcnew SumDelegate(MyX, &X::F);
   SumDelegate ^ pSD2 = gcnew SumDelegate(&X::F2);
}
```
