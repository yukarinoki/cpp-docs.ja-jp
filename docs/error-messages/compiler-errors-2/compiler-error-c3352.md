---
title: コンパイラ エラー C3352
ms.date: 11/04/2016
f1_keywords:
- C3352
helpviewer_keywords:
- C3352
ms.assetid: f233bed7-474e-425f-aad2-7801578169d4
ms.openlocfilehash: 6641f05c8daa5ad505c0bcb8d29a369ad5fd9a9a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58779600"
---
# <a name="compiler-error-c3352"></a>コンパイラ エラー C3352

'function': 指定された関数がデリゲート型 'type' と一致しません

パラメーターのリストが`function`とデリゲートが一致していません。

詳細については、[デリゲート (C++ コンポーネント拡張)](../../extensions/delegate-cpp-component-extensions.md)を参照してください。

次の例では、C3352 が生成されます。

```
// C3352.cpp
// compile with: /clr
delegate int D( int, int );
ref class C {
public:
   int mf( int ) {
      return 1;
   }

   // Uncomment the following line to resolve.
   // int mf(int, int) { return 1; }
};

int main() {
   C^ pC = gcnew C;
   System::Delegate^ pD = gcnew D( pC, &C::mf );   // C3352
}
```
