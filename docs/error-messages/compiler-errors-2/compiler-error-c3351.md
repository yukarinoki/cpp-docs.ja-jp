---
description: 詳細については、「コンパイラエラー C3351」を参照してください。
title: コンパイラ エラー C3351
ms.date: 11/04/2016
f1_keywords:
- C3351
helpviewer_keywords:
- C3351
ms.assetid: c021bbbe-1067-4f51-af4f-940d2b792eb5
ms.openlocfilehash: 324d927f0a54ea5750cbea45827152a66546cba7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144536"
---
# <a name="compiler-error-c3351"></a>コンパイラ エラー C3351

'object': デリゲート コンストラクター: 2 番目の引数は、静的メンバー関数またはグローバル関数のアドレスでなければなりません

コンパイラは、宣言された関数のアドレスを予期していました **`static`** 。

次の例では C3351 が生成されます。

```cpp
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
