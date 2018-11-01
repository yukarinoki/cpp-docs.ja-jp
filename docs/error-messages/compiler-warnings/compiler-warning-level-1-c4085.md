---
title: コンパイラの警告 (レベル 1) C4085
ms.date: 11/04/2016
f1_keywords:
- C4085
helpviewer_keywords:
- C4085
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
ms.openlocfilehash: cfd2296d2e58899bf818281716af2074c2f0ce91
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640753"
---
# <a name="compiler-warning-level-1-c4085"></a>コンパイラの警告 (レベル 1) C4085

プラグマに、'on' か 'off' のパラメーターが必要です。

プラグマには、 **on** または **off** パラメーターが必要です。 このプラグマは無視されます。

次の例では C4085 が生成されます。

```
// C4085.cpp
// compile with: /W1 /LD
#pragma optimize( "t", maybe )  // C4085
```