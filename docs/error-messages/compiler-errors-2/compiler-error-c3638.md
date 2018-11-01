---
title: コンパイラ エラー C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 8b1ef7f4cb38653f0ccdfae5684eb2907a735af7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50486893"
---
# <a name="compiler-error-c3638"></a>コンパイラ エラー C3638

'operator': 標準ボックス化とボックス化解除変換演算子を再定義することはできません

コンパイラは、暗黙的なボックス化をサポートするために、各マネージ クラスの変換演算子を定義します。 この演算子は再定義することはできません。

詳細については、次を参照してください。[暗黙的なボックス化](../../windows/boxing-cpp-component-extensions.md)します。

次の例では、C3638 が生成されます。

```
// C3638.cpp
// compile with: /clr
value struct V {
   V(){}
   static operator V^(V);   // C3638
};

int main() {
   V myV;
   V ^ pmyV = myV;   // operator supports implicit boxing
}
```