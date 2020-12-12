---
description: 詳細については、「コンパイラエラー C2624」を参照してください。
title: コンパイラエラー C2624
ms.date: 11/04/2016
f1_keywords:
- C2624
helpviewer_keywords:
- C2624
ms.assetid: 32f2ec15-a7cd-4049-a64b-131746d3152b
ms.openlocfilehash: 4fa52e5192bd71c9fcdd3608b4161d1e5da57bdf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97174677"
---
# <a name="compiler-error-c2624"></a>コンパイラエラー C2624

ローカルクラスを使用して ' extern ' 変数を宣言することはできません

ローカルクラスまたは構造体を使用して変数を宣言することはできません **`extern`** 。

次の例では、C2624 が生成されます。

```cpp
// C2624.cpp
int main() {
   struct C {};
   extern C ac;   // C2624
}
```
