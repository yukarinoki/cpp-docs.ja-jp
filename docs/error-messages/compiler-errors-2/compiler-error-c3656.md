---
description: 詳細については、「コンパイラエラー C3656」を参照してください。
title: コンパイラ エラー C3656
ms.date: 11/04/2016
f1_keywords:
- C3656
helpviewer_keywords:
- C3656
ms.assetid: 88965d85-73b0-4b35-8020-0650c9c94cd8
ms.openlocfilehash: ad87b989bf0e094a011ac5451745d5d296a0c223
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134434"
---
# <a name="compiler-error-c3656"></a>コンパイラ エラー C3656

' override ': オーバーライド指定子を繰り返すことはできません

明示的な override キーワードは一度だけ指定できます。 詳細については、「 [明示的なオーバーライド](../../extensions/explicit-overrides-cpp-component-extensions.md)」を参照してください。

次の例では、C3656 が生成されます。

```cpp
// C3656.cpp
// compile with: /clr /c
public interface struct O {
   int f();
};

public ref struct V : O {
   int f() override override { return 0; }   // C3656
   // try the following line instead
   // int f() override { return 0; }
};
```
