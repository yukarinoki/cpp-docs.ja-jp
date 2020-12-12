---
description: 詳細については、「コンパイラエラー C2586」を参照してください。
title: コンパイラ エラー C2586
ms.date: 11/04/2016
f1_keywords:
- C2586
helpviewer_keywords:
- C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
ms.openlocfilehash: bcf0c374936c994773f0c2d2afa56924d6ca9f4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177615"
---
# <a name="compiler-error-c2586"></a>コンパイラ エラー C2586

不適切なユーザー定義の変換構文です: 間接指定が無効です。

変換演算子の間接参照は許可されていません。

次の例では、C2586 が生成されます。

```cpp
// c2586.cpp
// compile with: /c
struct C {
   * operator int();   // C2586
   operator char();   // OK
};
```
