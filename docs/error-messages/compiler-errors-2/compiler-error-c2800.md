---
title: コンパイラ エラー C2800
ms.date: 11/04/2016
f1_keywords:
- C2800
helpviewer_keywords:
- C2800
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
ms.openlocfilehash: e893866a28c124e9e6cbc9663a488f89ac2d291b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516897"
---
# <a name="compiler-error-c2800"></a>コンパイラ エラー C2800

'operator 演算子' をオーバー ロードできません。

次の演算子をオーバー ロードできません: クラス メンバー アクセス (`.`)、メンバーへのポインター (`.*`)、スコープ解決 (`::`)、条件式 (`? :`)、および`sizeof`します。

次の例では、C2800 が生成されます。

```
// C2800.cpp
// compile with: /c
class C {
   operator:: ();   // C2800
};
```