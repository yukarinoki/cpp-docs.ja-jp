---
title: コンパイラの警告 (レベル 1) C4172
ms.date: 11/04/2016
f1_keywords:
- C4172
helpviewer_keywords:
- C4172
ms.assetid: a8d2bf65-d8b1-4fe3-8340-a223d7e7fde6
ms.openlocfilehash: 7258172c00b1ff4aebb18fa2c715559fd82a2180
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/24/2020
ms.locfileid: "80163547"
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
