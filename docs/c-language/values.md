---
title: 値
ms.date: 11/04/2016
ms.assetid: 24003f89-220f-4f93-be7a-b650c26157d7
ms.openlocfilehash: e0a200bfea8c0a0a06f064b280dad320da25550c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50534057"
---
# <a name="values"></a>値

**ANSI 3.1.2.5** 浮動小数点数のさまざまな型の表現と値セット

**float** 型は 32 ビットで、符号が 1 ビット、指数部が 8 ビット、仮数部が 23 ビットです。 その範囲は 7 桁以上の精度で、+/- 3.4E38 です。

**double** 型は 64 ビットで、符号が 1 ビット、指数部が 11 ビット、仮数部が 52 ビットです。 その範囲は 15 桁以上の精度で、+/- 1.7E308 です。

**long double** 型は 80 ビットで、符号が 1 ビット、指数部が 15 ビット、仮数部が 64 ビットです。 その範囲は 19 桁以上の精度で、+/- 1.2E4932 です。 Microsoft C コンパイラでは、**long double** 型の表現は **double** 型と同じであることに注意してください。

## <a name="see-also"></a>参照

[浮動小数点演算](../c-language/floating-point-math.md)