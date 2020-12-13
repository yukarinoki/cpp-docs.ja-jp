---
description: 詳細については、「コンパイラエラー C3380」を参照してください。
title: コンパイラ エラー C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: bb633d75d08fdbb902f086b3a4cd6a8a6db1fc69
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334986"
---
# <a name="compiler-error-c3380"></a>コンパイラ エラー C3380

'class': 無効なアセンブリ アクセス指定子です。'public' と 'private' のみ使用できます

マネージド クラスや構造体に適用される場合、 [public](../../cpp/public-cpp.md) キーワードと [private](../../cpp/private-cpp.md) キーワードはクラスがアセンブリ メタデータを通じて公開されるかどうかを示します。 `public` /clr `private` を指定してコンパイルされるプログラムのクラスには、 [または](../../build/reference/clr-common-language-runtime-compilation.md)以外は適用できません。

`ref`および `value` キーワード ( [/clr](../../build/reference/clr-common-language-runtime-compilation.md)と共に使用する場合) は、クラスがマネージであることを示します (「[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md)」を参照してください)。

次の例では C3380 が生成されます。

```cpp
// C3380_2.cpp
// compile with: /clr
protected ref class A {   // C3380
// try the following line instead
// ref class A {
public:
   static int i = 9;
};

int main() {
   A^ myA = gcnew A;
   System::Console::WriteLine(myA->i);
}
```
