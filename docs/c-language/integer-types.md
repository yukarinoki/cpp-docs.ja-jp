---
title: 整数型
ms.date: 07/22/2020
helpviewer_keywords:
- integer data type, integer types in C++
- integer constants
- integer types
- integers, types
ms.assetid: c8926a5e-0e98-4e37-9b05-ce97961379bd
ms.openlocfilehash: 61ed64c613bc88ed5bf62999ba77fa4090c1ec4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211802"
---
# <a name="integer-types"></a>整数型

各整数定数には、その値と表現方法に基づいて型が割り当てられます。 整数定数を **`long`** 型にするには、その定数の末尾に文字 **`l`** または **`L`** を追加します。整数定数を **`unsigned`** 型にするには、その値に **`u`** または **`U`** を追加します。 小文字の **`l`** は数字の 1 と区別しにくいので、使用しないでください。 次に、 **`long`** 整数定数の形式をいくつか示します。

```C
/* Long decimal constants */
10L
79L

/* Long octal constants */
012L
0115L

/* Long hexadecimal constants */
0xaL or 0xAL
0X4fL or 0x4FL

/* Unsigned long decimal constant */
776745UL
778866LU
```

定数に割り当てる型は、その定数が表す値に依存します。 定数の値は、その型で表現できる値範囲内にあることが条件となります。 式で定数を使用する場合やマイナス符号 ( **`-`** ) を適用する場合、定数がどのように変換されるかは、その定数の型によって決定されます。 整数定数の変換規則は次のとおりです。

- サフィックスのない 10 進定数の型は、 **`int`** 、 **`long int`** 、または **`unsigned long int`** です。 これら 3 つのうち、定数の値を表すことができる最初の型が定数に割り当てられます。

- サフィックスのない 8 進定数または 16 進定数に割り当てられる型は、 **`int`** 、 **`unsigned int`** 、 **`long int`** 、または **`unsigned long int`** です (定数のサイズによって異なります)。

- **`u`** または **`U`** サフィックスが指定された定数に割り当てられる型は、そのサイズに応じて **`unsigned int`** または **`unsigned long int`** です。

- **`l`** または **`L`** サフィックスが指定された定数に割り当てられる型は、そのサイズに応じて **`long int`** または **`unsigned long int`** です。

- **`u`** または **`U`** 、および **`l`** または **`L`** サフィックスが指定された定数に割り当てられる型は、 **`unsigned long int`** です。

## <a name="see-also"></a>関連項目

[C 整数定数](../c-language/c-integer-constants.md)
