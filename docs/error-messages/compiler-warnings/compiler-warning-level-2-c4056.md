---
description: '詳細情報: コンパイラの警告 (レベル 2) C4056'
title: コンパイラの警告 (レベル 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 5d8b96e97197e43bf288476e310ddd842a90ec48
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326545"
---
# <a name="compiler-warning-level-2-c4056"></a>コンパイラの警告 (レベル 2) C4056

浮動小数点定数演算のオーバーフロー

浮動小数点定数算術演算では、許容される最大値を超える結果が生成されます。

この警告は、定数演算中に実行されるコンパイラの最適化によって発生することがあります。 最適化 ([/od](../../build/reference/od-disable-debug.md)) をオフにしたときにこの警告が表示されない場合は、この警告を無視しても問題ありません。

次の例では、C4056 が生成されます。

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```
