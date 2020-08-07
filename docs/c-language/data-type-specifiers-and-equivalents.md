---
title: データ型指定子と同等物
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
ms.assetid: 0d4b515a-4f68-4786-83cf-a5d43c7cb6f3
ms.openlocfilehash: cc8ba746bea7f6ea885beb625de414d83367b53f
ms.sourcegitcommit: f2a135d69a2a8ef1777da60c53d58fe06980c997
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/03/2020
ms.locfileid: "87520682"
---
# <a name="data-type-specifiers-and-equivalents"></a>データ型指定子と同等物

このブックでは、通常、次の表に示す型指定子の短い形式を使用し、長い形式は使用しません。 **`char`** 型は既定で符号付きであることを前提としています。 そのため、このブックでは、 **`char`** は **`signed char`** と同等です。

## <a name="type-specifiers-and-equivalents"></a>型指定子と同等の形式

| 型指定子 | 同等の形式 |
|--|--|
| **`signed char`** <sup>1</sup> | **`char`** |
| **`signed int`** | **`signed`** , **`int`** |
| **`signed short int`** | **`short`** , **`signed short`** |
| **`signed long int`** | **`long`** , **`signed long`** |
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

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[C 型指定子](../c-language/c-type-specifiers.md)
