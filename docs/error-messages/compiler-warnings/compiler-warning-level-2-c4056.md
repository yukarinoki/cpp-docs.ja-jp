---
title: コンパイラの警告 (レベル 2) C4056 |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4056
dev_langs:
- C++
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6e069867d4aef749f9f6e42f46a34745d9e8aa62
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067508"
---
# <a name="compiler-warning-level-2-c4056"></a>コンパイラの警告 (レベル 2) C4056

浮動小数点定数演算でオーバーフローしました。

浮動小数点定数演算では、許容される最大値を超える結果が生成されます。

この警告を生成して、定数演算中に実行されるコンパイラ最適化されることができます。 最適化をオフにするときに発生する場合、この警告を無視しても問題ありません ([/Od](../../build/reference/od-disable-debug.md))。

次の例では、C4056 が生成されます。

```
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```