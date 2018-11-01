---
title: コンパイラ エラー C3288
ms.date: 11/04/2016
f1_keywords:
- C3288
helpviewer_keywords:
- C3288
ms.assetid: ed08a540-9751-46e1-9cbe-c51d6a49ffab
ms.openlocfilehash: 30a88d1047f8395fc8e3042cf2a1da88e6e5c2d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608417"
---
# <a name="compiler-error-c3288"></a>コンパイラ エラー C3288

'type': 無効なハンドル型の逆参照

ハンドル型の無効なを逆参照が検出されました。 ハンドル型を逆参照し、参照に割り当てることができます。 詳細については、次を参照してください。[参照演算子の追跡](../../windows/tracking-reference-operator-cpp-component-extensions.md)します。

## <a name="example"></a>例

次の例では、C3288 が生成されます。

```
// C3288.cpp
// compile with: /clr
ref class R {};
int main() {
   *(System::Object^) nullptr;   // C3288

// OK
   (System::Object^) nullptr;   // OK
   R^ r;
   R% pr = *r;
}
```