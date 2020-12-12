---
description: '詳細情報: コンパイラの警告 (レベル 1) C4172'
title: コンパイラの警告 (レベル 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7bcfe460150e543c1e3fb6a93ed6656619b5cb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97266937"
---
# <a name="compiler-warning-level-1-c4172"></a>コンパイラの警告 (レベル 1) C4172

ローカル変数または一時アドレスを返す

関数は、ローカル変数または一時オブジェクトのアドレスを返します。 ローカル変数と一時オブジェクトは、関数がを返したときに破棄されるので、返されたアドレスは無効です。

関数を再設計して、ローカルオブジェクトのアドレスが返されないようにします。

次の例では、C4172 が生成されます。

```cpp
// C4172.cpp
// compile with: /W1 /LD
float f = 10;

const double& bar() {
// try the following line instead
// const float& bar() {
   return f;   // C4172
}
```
