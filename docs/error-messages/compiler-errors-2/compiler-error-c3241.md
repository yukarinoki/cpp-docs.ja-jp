---
description: 詳細については、「コンパイラエラー C3241」を参照してください。
title: コンパイラ エラー C3241
ms.date: 11/04/2016
f1_keywords:
- C3241
helpviewer_keywords:
- C3241
ms.assetid: 2ca14879-bba0-4a23-b22a-72cfff92d6a4
ms.openlocfilehash: c940599ccee67338c6a088793970b7a255d83ff2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307341"
---
# <a name="compiler-error-c3241"></a>コンパイラ エラー C3241

' method ': このメソッドは ' interface ' によって導入されていません

関数を明示的にオーバーライドする場合、関数のシグネチャは、オーバーライドする関数の宣言と完全に一致する必要があります。

次の例では、C3241 が生成されます。

```cpp
// C3241.cpp
#pragma warning(disable:4199)

__interface IX12A {
   void mf();
};

__interface IX12B {
   void mf(int);
};

class CX12 : public IX12A, public IX12B { // C3241
   void IX12A::mf(int);
};
```
