---
title: コンパイラ エラー C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: c8f2252c05e3e264740004f4126c7557f30b126a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657333"
---
# <a name="compiler-error-c3662"></a>コンパイラ エラー C3662

'member': オーバーライド指定子 'specifier' は、マネージドまたは WinRT クラスのメンバー関数でのみ使用できます

オーバーライド指定子が、ネイティブ型のメンバーで使用されました。これは許可されていません。

詳細については、次を参照してください。[明示的なオーバーライド](../../windows/explicit-overrides-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では C3662 が生成されます。

```
// C3662.cpp
// compile with: /clr /c
struct S {
   virtual void f();
};

struct S1 : S {
   virtual void f() new;   // C3662
};

ref struct T {
   virtual void f();
};

ref struct T1 : T {
   virtual void f() new;   // OK
};
```