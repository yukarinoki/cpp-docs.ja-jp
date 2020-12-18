---
description: '詳細情報: 整数の浮動小数点値へのキャスト'
title: 整数の浮動小数点値へのキャスト
ms.date: 11/04/2016
helpviewer_keywords:
- integers, casting to floating-point values
ms.assetid: 81fd5b7d-15eb-4c11-a8c8-e1621ff54fd3
ms.openlocfilehash: 2a1a3ce5bf7aac98148c70eb62cdb3c377ca54f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214019"
---
# <a name="casting-integers-to-floating-point-values"></a>整数の浮動小数点値へのキャスト

**ANSI 3.2.1.3** 整数を、元の値を正確に表現できない浮動小数点数に変換する場合の切り捨てまたは丸めの方向

整数を、元の値を正確に表現できない浮動小数点数値にキャストすると、最も近い適切な値に切り上げまたは切り下げられます。

たとえば、 **`unsigned long`** (32 ビット精度) を **`float`** (仮数が 23 ビット精度) にキャストすると、最も近い 256 の倍数に丸められます。 **`long`** 値 4,294,966,913 から 4,294,967,167 はすべて、 **`float`** 値 4,294,967,040 に丸められます。

## <a name="see-also"></a>関連項目

[浮動小数点演算](../c-language/floating-point-math.md)
