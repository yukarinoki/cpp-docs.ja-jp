---
title: コンパイラ エラー C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 2d6b2cb15cfaa0b72b946c0edb3b451737b51772
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553505"
---
# <a name="compiler-error-c3379"></a>コンパイラ エラー C3379

'class': 入れ子になったクラス宣言の一部としてアセンブリ アクセス指定子を含めることはできません

クラスまたは構造体などのマネージ型に適用すると、[パブリック](../../cpp/public-cpp.md)と[プライベート](../../cpp/private-cpp.md)キーワードは、クラスがアセンブリ メタデータを通じて公開するかどうかを示します。 `public` または`private`は外側のクラスのアセンブリのアクセス権を継承する入れ子になったクラスに適用することはできません。

使用すると[/clr](../../build/reference/clr-common-language-runtime-compilation.md)、`ref`と`value`キーワードは、クラスが管理されていることを示します (を参照してください[クラスと構造体](../../windows/classes-and-structs-cpp-component-extensions.md))。

次の例では、C3379 が生成されます。

```
// C3379a.cpp
// compile with: /clr
using namespace System;

public ref class A {
public:
   static int i = 9;

   public ref class BA {   // C3379
   // try the following line instead
   // ref class BA {
   public:
      static int ii = 8;
   };
};

int main() {

   A^ myA = gcnew A;
   Console::WriteLine(myA->i);

   A::BA^ myBA = gcnew A::BA;
   Console::WriteLine(myBA->ii);
}
```
