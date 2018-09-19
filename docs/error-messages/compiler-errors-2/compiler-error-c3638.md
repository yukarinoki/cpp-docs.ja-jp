---
title: コンパイラ エラー C3638 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3638
dev_langs:
- C++
helpviewer_keywords:
- C3638
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6f1d135dd69155de39b097d59cf139eb47354d4f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46107686"
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