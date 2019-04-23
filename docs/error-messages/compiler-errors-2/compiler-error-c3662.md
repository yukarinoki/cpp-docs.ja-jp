---
title: コンパイラ エラー C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: 28d8df02d63fc1b16a392a2df83524cd616d5ab3
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/18/2019
ms.locfileid: "59777306"
---
# <a name="compiler-error-c3662"></a>コンパイラ エラー C3662

'member': オーバーライド指定子 'specifier' は、マネージドまたは WinRT クラスのメンバー関数でのみ使用できます

オーバーライド指定子が、ネイティブ型のメンバーで使用されました。これは許可されていません。

詳細については、次を参照してください。[明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)します。

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