---
title: コンパイラの警告 (レベル 1 および 4) C4112
ms.date: 11/04/2016
f1_keywords:
- C4112
helpviewer_keywords:
- C4112
ms.assetid: aff64897-bb79-4a67-9b6f-902c6d44f3dc
ms.openlocfilehash: 3678d0ce5d9eb9568f0272da4173e72502b0557f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50655833"
---
# <a name="compiler-warning-levels-1-and-4-c4112"></a>コンパイラの警告 (レベル 1 および 4) C4112

\#行が 1 から数までの整数が必要です。

許可された範囲を超えた整数パラメーターが [#line](../../preprocessor/hash-line-directive-c-cpp.md) ディレクティブに指定されています。

指定したパラメーターが 1 より小さい場合、行カウンターは 1 にリセットされます。 指定したパラメーターが、コンパイラで定義された制限値である *number*より大きい場合、行カウンターは変更されません。 これは、ANSI 互換オプション ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) ではレベル 1 の警告であり、Microsoft 拡張機能オプション ([/Ze](../../build/reference/za-ze-disable-language-extensions.md)) ではレベル 4 の警告です。

次の例では C4112 が生成されます。

```
// C4112.cpp
// compile with: /W4
#line 0   // C4112, value must be between 1 and number

int main() {
}
```