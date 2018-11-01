---
title: コンパイラ エラー C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 2114ad048c2061b81f223c86536f23737bdf43fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50540063"
---
# <a name="compiler-error-c2516"></a>コンパイラ エラー C2516

'name': 有効な基本クラスではありません

クラスで定義された型名から、`typedef`ステートメント。

次の例では、C2516 が生成されます。

```
// C2516.cpp
typedef unsigned long ulong;
class C : public ulong {}; // C2516
```