---
title: コンパイラの警告 (レベル 2) C4756
ms.date: 11/04/2016
f1_keywords:
- C4756
helpviewer_keywords:
- C4756
ms.assetid: 5a16df83-6b82-4619-83bd-319af4ef1d1d
ms.openlocfilehash: 0e4e0d5e227795a45eb22e3fcb17bdfa600d69e9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622522"
---
# <a name="compiler-warning-level-2-c4756"></a>コンパイラの警告 (レベル 2) C4756

定数演算でオーバーフローしました。

コンパイラには、コンパイル時に定数演算を実行中に例外が生成されます。

次の例では、C4756 が生成されます。

```
// C4756.cpp
// compile with: /W2 /Od
int main()
{
   float f = 1e100+1e100;   // C4756
}
```