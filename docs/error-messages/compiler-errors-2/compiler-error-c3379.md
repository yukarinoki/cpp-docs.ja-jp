---
description: 詳細については、「コンパイラエラー C3379」を参照してください。
title: コンパイラ エラー C3379
ms.date: 11/04/2016
f1_keywords:
- C3379
helpviewer_keywords:
- C3379
ms.assetid: a66c2c4e-091c-4426-9cde-7c4cfb2ffce1
ms.openlocfilehash: 622a1327eb84d83fa24d8a084e3266183c669120
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97220735"
---
# <a name="compiler-error-c3379"></a>コンパイラ エラー C3379

' class ': 入れ子になったクラスは、宣言の一部としてアセンブリアクセス指定子を持つことはできません

クラスや構造体などのマネージ型に適用される場合、 [public](../../cpp/public-cpp.md) キーワードと [private](../../cpp/private-cpp.md) キーワードは、クラスがアセンブリメタデータを通じて公開されるかどうかを示します。 `public` またはは、 `private` 外側のクラスのアセンブリアクセスを継承する、入れ子になったクラスには適用できません。

[/Clr](../../build/reference/clr-common-language-runtime-compilation.md)と共に使用する場合、 `ref` キーワードとキーワードは、 `value` クラスがマネージであることを示します (「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください)。

次の例では、C3379 が生成されます。

```cpp
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
