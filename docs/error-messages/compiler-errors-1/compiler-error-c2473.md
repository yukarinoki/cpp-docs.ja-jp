---
title: コンパイラ エラー C2473
ms.date: 11/04/2016
f1_keywords:
- C2473
helpviewer_keywords:
- C2473
ms.assetid: 6bb7dbf5-b198-490f-860e-fd64d0c2a284
ms.openlocfilehash: 232f89a714d70c6914b73a370c5f658ff4283ab4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631791"
---
# <a name="compiler-error-c2473"></a>コンパイラ エラー C2473

'identifier': 関数定義のようですが、パラメーター リストがありません。

関数と思われるものが検出されましたが、パラメーター リストがありません。

## <a name="example"></a>例

次の例では C2473 が生成されます。

```
// C2473.cpp
// compile with: /clr /c
class A {
   int i {}   // C2473
};

class B {
   int i() {}   // OK
};
```