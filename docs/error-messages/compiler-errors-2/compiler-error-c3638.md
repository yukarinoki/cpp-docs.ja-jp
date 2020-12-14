---
description: 詳細については、「コンパイラエラー C3638」を参照してください。
title: コンパイラ エラー C3638
ms.date: 11/04/2016
f1_keywords:
- C3638
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
ms.openlocfilehash: 1d1cc59cd8065a5b0e661292b717ba885c6febeb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97239195"
---
# <a name="compiler-error-c3638"></a>コンパイラ エラー C3638

' operator ': 標準のボックス化およびボックス化解除変換演算子を再定義することはできません

コンパイラは、暗黙的なボックス化をサポートするために、各マネージクラスの変換演算子を定義します。 この演算子を再定義することはできません。

詳細については、「 [暗黙的なボックス](../../extensions/boxing-cpp-component-extensions.md)化」を参照してください。

次の例では、C3638 が生成されます。

```cpp
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
