---
title: ポインターの減算
ms.date: 11/04/2016
helpviewer_keywords:
- pointer subtraction
ms.assetid: 4d515690-088a-43f6-bb8c-57b849f7ccf7
ms.openlocfilehash: c978c3bf11a2c82071d78e37511ac32a951209f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50468472"
---
# <a name="pointer-subtraction"></a>ポインターの減算

**ANSI 3.3.6, 4.1.1** 同じ配列の要素への 2 つのポインター間の差を保持するために必要な整数型、**ptrdiff_t**

`ptrdiff_t` は、32 ビット x86 プラットフォームでは `int` です。 64 ビット プラットフォームでは、`ptrdiff_t` typedef は `__int64` です。

## <a name="see-also"></a>参照

[配列とポインター](../c-language/arrays-and-pointers.md)
