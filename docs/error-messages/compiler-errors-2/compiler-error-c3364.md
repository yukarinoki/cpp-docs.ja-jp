---
description: 詳細については、「コンパイラエラー C3364」を参照してください。
title: コンパイラ エラー C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: e500b984489de1dfc2cd68d91ac5cb457d3887f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150853"
---
# <a name="compiler-error-c3364"></a>コンパイラ エラー C3364

' delegate ': delegate コンストラクター: 引数はマネージクラスまたはグローバル関数のメンバー関数へのポインターでなければなりません

デリゲートのコンストラクターの2番目のパラメーターは、メンバー関数のアドレス、または任意のクラスの静的メンバー関数のアドレスのいずれかを受け取ります。 どちらも単純なアドレスとして扱われます。

次の例では、C3364 が生成されます。

```cpp
// C3364_2.cpp
// compile with: /clr

delegate int D( int, int );

ref class C {
public:
   int mf( int, int ) {
      return 1;
   }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC,pC->mf( 1, 2 ) ); // C3364

   // try the following line instead
   // System::Delegate^ pD = gcnew D(pC, &C::mf);
}
```
