---
title: コンパイラ エラー C2194
ms.date: 11/04/2016
f1_keywords:
- C2194
helpviewer_keywords:
- C2194
ms.assetid: df6e631c-0062-4844-9088-4cc7a0ff879f
ms.openlocfilehash: 6059b54c0b30bd11e1c8bc6f3779f4739d344ff7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537216"
---
# <a name="compiler-error-c2194"></a>コンパイラ エラー C2194

'identifier': テキスト セグメント

`data_seg`プラグマで使用されるセグメント名を使用して`code_seg`します。

次の例では、C2194 が生成されます。

```
// C2194.cpp
// compile with: /c
#pragma code_seg("MYCODE")
#pragma data_seg("MYCODE")   // C2194
#pragma data_seg("MYCODE2")   // OK
```