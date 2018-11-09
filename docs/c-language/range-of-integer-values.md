---
title: Range of Integer Values (整数値の範囲)
ms.date: 11/04/2016
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
ms.openlocfilehash: bcf79877ed1bbd261a70b56d60df86adc31c897b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50632041"
---
# <a name="range-of-integer-values"></a>Range of Integer Values (整数値の範囲)

**ANSI 3.1.2.5** 整数のさまざまな型の表現と値セット

整数は 32 ビット (4 バイト) を含みます。 符号付き整数は、2 の補数形式で表されます。 最上位ビットは符号を表し、負の数ならば 1、正の数とゼロならば 0 です。 値は次のとおりです。

|型|最小および最大|
|----------|-------------------------|
|**unsigned short**|0 から 65535|
|`signed short`|-32768 から 32767|
|`unsigned long`|0 から 4294967295|
|**signed long**|-2147483648 から 2147483647|

## <a name="see-also"></a>参照

[整数](../c-language/integers.md)