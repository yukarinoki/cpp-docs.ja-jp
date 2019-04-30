---
title: コンパイラ エラー C2516
ms.date: 11/04/2016
f1_keywords:
- C2516
helpviewer_keywords:
- C2516
ms.assetid: cd3accc1-0179-4a13-9587-616908c4ad1d
ms.openlocfilehash: 2114ad048c2061b81f223c86536f23737bdf43fb
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64344761"
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