---
title: コンパイラの警告 (レベル 1) C4068
ms.date: 11/04/2016
f1_keywords:
- C4068
helpviewer_keywords:
- C4068
ms.assetid: 96a7397a-4eab-44ab-b3bb-36747503f7e5
ms.openlocfilehash: 1e0cb7229733e15afd87548a1b18b3f58a64c239
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50565075"
---
# <a name="compiler-warning-level-1-c4068"></a>コンパイラの警告 (レベル 1) C4068

不明なプラグマがありました。

コンパイラで、認識できない [プラグマ](../../preprocessor/pragma-directives-and-the-pragma-keyword.md)が無視されました。 この **プラグマ** が使用中のコンパイラで許可されていることを確認してください。 次の例では C4068 が生成されます。

```
// C4068.cpp
// compile with: /W1
#pragma NotAValidPragmaName   // C4068, use valid name to resolve
int main()
{
}
```