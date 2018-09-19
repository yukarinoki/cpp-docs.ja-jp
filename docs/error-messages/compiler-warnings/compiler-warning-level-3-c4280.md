---
title: コンパイラの警告 (レベル 3) C4280 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4280
dev_langs:
- C++
helpviewer_keywords:
- C4280
ms.assetid: 153fb639-3ee1-4fee-baf9-71420abcf3f6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa1446e6725ecbb990e38ede33071afddb54065f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46118324"
---
# <a name="compiler-warning-level-3-c4280"></a>コンパイラの警告 (レベル 3) C4280

自己再帰的な型を 'type' が 'operator ->'

コードは正しくない、 **operator ->** 自体を呼び出す。

次の例では、C4280 が生成されます。

```
// C4280.cpp
// compile with: /W3 /WX
struct A
{
   int z;
   A& operator ->();
};

void f(A y)
{
   int i = y->z; // C4280
}
```