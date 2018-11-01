---
title: コンパイラ エラー C2108
ms.date: 11/04/2016
f1_keywords:
- C2108
helpviewer_keywords:
- C2108
ms.assetid: c84f0b47-5e2c-47d2-8edb-427a40e17c36
ms.openlocfilehash: 3979fce67f1ecb7f78bd02d4f1c4d2cca287ceca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628216"
---
# <a name="compiler-error-c2108"></a>コンパイラ エラー C2108

添字に整数でない型が使われました。

配列の添字が整数式ではありません。

## <a name="example"></a>例

C2108 が正しくない使用する場合に発生、`this`型の既定のインデクサーにアクセスする値型のポインター。 詳細については、次を参照してください。[セマンティクスは、このポインター](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)します。

次の例では、C2108 が生成されます。

```
// C2108.cpp
// compile with: /clr
using namespace System;

value struct B {
   property Double default[Double] {
      Double get(Double data) {
         return data*data;
      }
   }
   void Test() {
      Console::WriteLine("{0}", this[3.3]);   // C2108
      Console::WriteLine("{0}", this->default[3.3]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```