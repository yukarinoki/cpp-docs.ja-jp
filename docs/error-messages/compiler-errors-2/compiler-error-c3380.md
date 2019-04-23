---
title: コンパイラ エラー C3380
ms.date: 11/04/2016
f1_keywords:
- C3380
helpviewer_keywords:
- C3380
ms.assetid: 86f1f4ec-4ad8-4a1a-9b6c-2d9b6129df6b
ms.openlocfilehash: 516690f2524d48e7abbf7546592c6346e92c3e2e
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59778866"
---
# <a name="compiler-error-c3380"></a>コンパイラ エラー C3380

'class': 無効なアセンブリ アクセス指定子です。'public' と 'private' のみ使用できます

マネージド クラスや構造体に適用される場合、 [public](../../cpp/public-cpp.md) キーワードと [private](../../cpp/private-cpp.md) キーワードはクラスがアセンブリ メタデータを通じて公開されるかどうかを示します。 `public` /clr `private` を指定してコンパイルされるプログラムのクラスには、 [または](../../build/reference/clr-common-language-runtime-compilation.md)以外は適用できません。

`ref`と`value`で使用する場合は、キーワード[/clr](../../build/reference/clr-common-language-runtime-compilation.md)、クラスが管理されていることを示します (を参照してください[クラスと構造体](../../extensions/classes-and-structs-cpp-component-extensions.md))。

次の例では C3380 が生成されます。

```
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
