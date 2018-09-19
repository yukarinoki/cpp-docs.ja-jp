---
title: コンパイラ エラー C3364 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3364
dev_langs:
- C++
helpviewer_keywords:
- C3364
ms.assetid: 98654741-60fe-4472-a6af-e580f8c0a6e1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 65ac2c54ccd0fe4a086cfcc79cf4dba269876ad3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46096250"
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
