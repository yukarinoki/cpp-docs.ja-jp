---
description: '詳細情報: コンパイラの警告 (レベル 4) C4481'
title: コンパイラの警告 (レベル 4) C4481
ms.date: 11/04/2016
f1_keywords:
- C4481
helpviewer_keywords:
- C4481
ms.assetid: 7bfd4e0c-b452-4e6c-b7c4-ac5cc93fe4ea
ms.openlocfilehash: 463df18090a4f6f632a80543576db4cb9048e754
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251298"
---
# <a name="compiler-warning-level-4-c4481"></a>コンパイラの警告 (レベル 4) C4481

非標準の拡張が使用されています: オーバーライド指定子 ' keyword '

C++ 標準に含まれていないキーワードが使用されました。たとえば、/clr でも動作するオーバーライド指定子の1つです。  詳細については、次のトピックを参照してください。

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [オーバーライド指定子](../../extensions/override-specifiers-cpp-component-extensions.md)

## <a name="example"></a>例

次の例では、C4481 が生成されます。

```cpp
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
