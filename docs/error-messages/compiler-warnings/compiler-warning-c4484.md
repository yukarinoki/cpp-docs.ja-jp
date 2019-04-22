---
title: コンパイラの警告 C4484
ms.date: 11/04/2016
f1_keywords:
- C4484
helpviewer_keywords:
- C4484
ms.assetid: 3d30e5b3-2297-45b7-a37a-1360056fdd0e
ms.openlocfilehash: 29e99da02aa0144699d3c20e523b5e5e4b6b8f72
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "58766801"
---
# <a name="compiler-warning-c4484"></a>コンパイラの警告 C4484

'override_function': 基本 ref クラス メソッド 'base_class_function' と一致しますが、'virtual'、'new' または 'override'; に、設定されていません'new' (および 'virtual') と見なされます

コンパイルするときに **/clr**コンパイラは暗黙的には、関数が、vtable の新しいスロットを取得することを意味、基底クラスの関数をオーバーライドしません。 解決するには、明示的に関数がオーバーライドがかどうかを指定します。

詳細については次を参照してください:

- [/clr (共通言語ランタイムのコンパイル)](../../build/reference/clr-common-language-runtime-compilation.md)

- [override](../../extensions/override-cpp-component-extensions.md)

- [new (vtable の新しいスロット)](../../extensions/new-new-slot-in-vtable-cpp-component-extensions.md)

C4484 は常に、エラーとして発行されます。 使用して、[警告](../../preprocessor/warning.md)C4484 を抑制するプラグマ。

## <a name="example"></a>例

次の例では、C4484 が生成されます。

```
// C4484.cpp
// compile with: /clr
ref struct A {
   virtual void Test() {}
};

ref struct B : A {
   void Test() {}   // C4484
};

// OK
ref struct C {
   virtual void Test() {}
   virtual void Test2() {}
};

ref struct D : C {
   virtual void Test() new {}
   virtual void Test2() override {}
};
```