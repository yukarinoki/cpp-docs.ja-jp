---
description: 詳細については、「コンパイラエラー C2107」を参照してください。
title: コンパイラ エラー C2107
ms.date: 11/04/2016
f1_keywords:
- C2107
helpviewer_keywords:
- C2107
ms.assetid: 2866a121-884e-4bb5-8613-36de5817000e
ms.openlocfilehash: aee5e7384f3d0a58265d1cc36448c7fb49c71f4f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335276"
---
# <a name="compiler-error-c2107"></a>コンパイラ エラー C2107

無効なインデックスです、間接参照は許可されていません

ポインターではない式に添字が使われています。

## <a name="example"></a>例

C2107 は、 **`this`** 型の既定のインデクサーにアクセスするために値型のポインターを誤って使用した場合に発生する可能性があります。 詳細については、「 [this ポインターのセマンティクス](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Semantics_of_the_this_pointer)」を参照してください。

次の例では、C2107 が生成されます。

```cpp
// C2107.cpp
// compile with: /clr
using namespace System;

value struct B {
   property String ^ default[String ^] {
      String ^ get(String ^ data) {
         return "abc";
      }
   }
   void Test() {
      Console::WriteLine("{0}", this["aa"]);   // C2107
      Console::WriteLine("{0}", this->default["aa"]);   // OK
   }
};

int main() {
   B ^ myb = gcnew B();
   myb->Test();
}
```
