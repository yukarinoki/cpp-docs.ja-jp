---
title: コンパイラの警告 (レベル 3) C4390
ms.date: 11/04/2016
f1_keywords:
- C4390
helpviewer_keywords:
- C4390
ms.assetid: c95c2f1b-9bce-4b1f-a80c-565d4cde0b1e
ms.openlocfilehash: 4ca00f892adc8fe3ac1bffb59a27ea1744249dea
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50479522"
---
# <a name="compiler-warning-level-3-c4390"></a>コンパイラの警告 (レベル 3) C4390

';'。 空の被制御文が見つかりました。目的ですか。

手順が含まれていない制御ステートメントの後にセミコロンが見つかりました。

マクロにより C4390 を取得する場合は使用、[警告](../../preprocessor/warning.md)プラグマ マクロを含むモジュールで C4390 を無効にします。

次の例では、C4390 が生成されます。

```
// C4390.cpp
// compile with: /W3
int main() {
   int i = 0;
   if (i);   // C4390
      i++;
}
```