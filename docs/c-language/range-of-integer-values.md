---
title: Range of Integer Values (整数値の範囲)
ms.date: 11/04/2016
ms.assetid: 0e9c6161-8f3f-4bfb-9fcc-a6c8dc97d702
ms.openlocfilehash: e34e700df203004388cd912089711b5849e00fd7
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343121"
---
# <a name="range-of-integer-values"></a>Range of Integer Values (整数値の範囲)

**ANSI 3.1.2.5** 整数のさまざまな型の表現と値セット

整数は 32 ビット (4 バイト) を含みます。 符号付き整数は、2 の補数形式で表されます。 最上位ビットにより符号が保持されます。負の場合は 1、正および 0 の場合は 0 です。 値は次のとおりです。

|種類|最小および最大|
|----------|-------------------------|
|**unsigned short**|0 から 65535|
|`signed short`|-32768 から 32767|
|`unsigned long`|0 から 4294967295|
|**signed long**|-2147483648 から 2147483647|

## <a name="see-also"></a>関連項目

[整数](../c-language/integers.md)
