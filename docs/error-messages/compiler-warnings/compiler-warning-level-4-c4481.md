---
title: コンパイラの警告 (レベル 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: fe96ff50f4081e3c9dbe3c7eb68da156a69c96ab
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776366"
---
# <a name="compiler-warning-level-4-c4481"></a>コンパイラの警告 (レベル 4) C4481

使用される標準の拡張機能: オーバーライド指定子 'keyword'

/Clr でも動作するオーバーライド指定子のいずれかの例では、C++ 標準ではないキーワードが使用されました。  詳細については、次のトピックを参照してください。

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [オーバーライド指定子](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>例

次の例では、C4481 が生成されます。

```
// C4481.cpp
// compile with: /W4 /c
class B {
   virtual void f(unsigned);
};

class C : B {
   void f(unsigned) override;   // C4481
   void f2(unsigned);
};
```