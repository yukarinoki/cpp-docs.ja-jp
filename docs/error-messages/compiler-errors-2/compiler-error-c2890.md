---
title: コンパイラ エラー C2890
ms.date: 11/04/2016
f1_keywords:
- C2890
helpviewer_keywords:
- C2890
ms.assetid: 49147375-182c-42b1-b170-f475cd436d47
ms.openlocfilehash: 43c05fba15ee78c8e1454c115246f557f98f897e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50661475"
---
# <a name="compiler-error-c2890"></a>コンパイラ エラー C2890

'class': ref クラスは、1 つのインターフェイスではない基本クラスを持つことができますのみ

参照クラスには、基底クラスの 1 つだけ設定できます。

次の例では、C2890 が生成されます。

```
// C2890.cpp
// compile with: /clr /c
ref class A {};
ref class B {};
ref class C : public A, public B {};   // C2890
ref class D : public A {};   // OK
```
