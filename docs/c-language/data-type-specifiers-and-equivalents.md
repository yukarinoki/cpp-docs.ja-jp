---
title: データ型指定子と同等物
description: Microsoft Visual C のデータ型指定子とそれらと同等のものについて説明します。
ms.date: 11/04/2016
helpviewer_keywords:
- type specifiers [C++], list
- widening integers
- data types [C++], equivalents
- sign-extending integral types
- zero-extending
- identifiers, data type
- data types [C++], specifiers
- simple types, names
- type names [C++], simple
ms.openlocfilehash: 6a1231bc19617dddf1cc01d4c5e7db2863f1055f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97207047"
---
# <a name="data-type-specifiers-and-equivalents"></a>データ型指定子と同等物

このドキュメントでは、通常、次の表に示す型指定子の短い形式を使用し、長い形式は使用しません。 また、 **`char`** 型は既定で符号付きであることを前提としています。 このドキュメント全体を通して、 **`char`** は **`signed char`** と同等です。

## <a name="type-specifiers-and-equivalents"></a>型指定子と同等物

| 型指定子 | 同等の形式 |
|--|--|
| **`signed char`** <sup>1</sup> | **`char`** |
| **`signed int`** | **`signed`** , **`int`** |
| **`signed short int`** | **`short`**, **`signed short`** |
| **`signed long int`** | **`long`**, **`signed long`** |
| **`unsigned char`** | — |
| **`unsigned int`** | **`unsigned`** |
| **`unsigned short int`** | **`unsigned short`** |
| **`unsigned long int`** | **`unsigned long`** |
| **`float`** | — |
| **`long double`** <sup>2</sup> | — |

<sup>1</sup> **`char`** 型を既定で unsigned にすると ( **`/J`** コンパイラ オプションを指定)、 **`signed char`** を **`char`** と短縮できません。

<sup>2</sup> 32 ビットまたは 64 ビット オペレーティング システムの Microsoft C コンパイラでは **`long double`** が **`double`** 型にマップされます。

**Microsoft 固有の仕様**

**`/J`** コンパイラ オプションを指定して、既定の **`char`** 型を **`signed char`** から **`unsigned char`** に変更できます。 このオプションが有効になっている場合、 **`char`** は **`unsigned char`** と同じ意味であり、符号付き文字の値を宣言するには **`signed`** キーワードを使用する必要があります。 **`char`** 値を明示的に **`signed`** 宣言すると、 **`/J`** オプションは適用されません。 **`int`** 型に上位変換すると、値が符号拡張されます。 **`char`** 型は、 **`int`** 型に上位変換するとゼロ拡張されます。

**Microsoft 固有の仕様の終了**

## <a name="see-also"></a>関連項目

[C 型指定子](../c-language/c-type-specifiers.md)
