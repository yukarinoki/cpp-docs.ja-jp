---
description: 詳細については、「コンパイラエラー C2111」を参照してください。
title: コンパイラ エラー C2111
ms.date: 11/04/2016
f1_keywords:
- C2111
helpviewer_keywords:
- C2111
ms.assetid: 38fd42ec-1480-4a44-aaca-ae4593ed5f50
ms.openlocfilehash: 604e793d787ceabd761d76146108df4b687c1e3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341257"
---
# <a name="compiler-error-c2111"></a>コンパイラ エラー C2111

'+': ポインターに整数でない値を加えようとしました

プラス ( `+` ) 演算子を使用してポインターに整数でない値を追加しようとしました。

次の例では C2111 が生成されます。

```cpp
// C2111.cpp
int main() {
   int *a = 0, *pa = 0, b = 0;
   double d = 0.00;

   a = pa + d;   // C2111
   a = pa + b;   // OK
}
```
