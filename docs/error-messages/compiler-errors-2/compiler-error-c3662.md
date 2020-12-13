---
description: 詳細については、「コンパイラエラー C3662」を参照してください。
title: コンパイラ エラー C3662
ms.date: 11/04/2016
f1_keywords:
- C3662
helpviewer_keywords:
- C3662
ms.assetid: 61bd3e41-a86b-42c0-be89-d992d3906ff1
ms.openlocfilehash: a62ffc4d5dc6083f36bab1e4e0712d942f70facf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134291"
---
# <a name="compiler-error-c3662"></a>コンパイラ エラー C3662

'member': オーバーライド指定子 'specifier' は、マネージドまたは WinRT クラスのメンバー関数でのみ使用できます

オーバーライド指定子が、ネイティブ型のメンバーで使用されました。これは許可されていません。

詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

## <a name="example"></a>例

次の例では C3662 が生成されます。

```cpp
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
