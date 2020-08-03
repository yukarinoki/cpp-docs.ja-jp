---
title: Demotion of Integers (整数の下位変換)
ms.date: 11/04/2016
helpviewer_keywords:
- demoting integers
ms.assetid: 51fb3654-60b0-4de7-80eb-bd910086c18a
ms.openlocfilehash: aee0a5041cd37b1fbad785b760b8cefde74eb195
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218885"
---
# <a name="demotion-of-integers"></a>Demotion of Integers (整数の下位変換)

**ANSI 3.2.1.2** 値を表すことができない場合に、整数を短い符号付き整数に変換したか、符号なし整数を同じ長さの符号付き整数に変換したときの結果

**`long`** 整数が **`short`** にキャストされるか、 **`short`** が **`char`** にキャストされるときには、下位バイトが保持されます。

たとえば、次のコード行、

```
short x = (short)0x12345678L;
```

では、値 0x5678 が `x` に代入されます。また、次のコード行、

```
char y = (char)0x1234;
```

では、値 0x34 が `y` に代入されます。

**`signed`** 変数が **`unsigned`** に変換されるときと、その逆で、ビット パターンは変わりません。 たとえば、-2 (0xFE) を **`unsigned`** 値にキャストすると、254 (これも 0xFE) になります。

## <a name="see-also"></a>関連項目

[整数](../c-language/integers.md)
