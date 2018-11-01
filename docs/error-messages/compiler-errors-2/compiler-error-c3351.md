---
title: コンパイラ エラー C3351
ms.date: 11/04/2016
f1_keywords:
- C3351
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
ms.openlocfilehash: 3935acc645403efcd579a80340ebb9794bc1052a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511684"
---
# <a name="compiler-error-c3351"></a>コンパイラ エラー C3351

'object': デリゲート コンストラクター: 2 番目の引数は、静的メンバー関数またはグローバル関数のアドレスでなければなりません

コンパイラには、 `static`として宣言された関数のアドレスが必要です。

次の例では C3351 が生成されます。

```
// C3351a.cpp
// compile with: /clr
delegate int D(int, int);

ref class C {
public:
   int mf(int, int) {
      return 1;
   }

   static int mf2(int, int) {
      return 1;
   }
};

int main() {
   System::Delegate ^pD = gcnew D(nullptr, &C::mf);   // C3351
   System::Delegate ^pD2 = gcnew D(&C::mf2);
}
```
