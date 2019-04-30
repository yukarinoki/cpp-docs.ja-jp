---
title: コンパイラ エラー C3364
ms.date: 11/04/2016
f1_keywords:
- C3364
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
ms.openlocfilehash: e99ab3919edcfb883701c08c52cd7aad60cd4591
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62400358"
---
# <a name="compiler-error-c3364"></a>コンパイラ エラー C3364

'delegate': delegate コンス トラクター: 引数はマネージ クラスのメンバー関数またはグローバル関数へのポインターである必要があります

デリゲートのコンス トラクターの 2 番目のパラメーターは、メンバー関数のアドレスまたは任意のクラスの静的メンバー関数のアドレスのいずれかを取得します。 両方は、単純なアドレスとして扱われます。

次の例では、C3364 が生成されます。

```
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
