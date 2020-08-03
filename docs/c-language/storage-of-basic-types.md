---
title: 基本型のストレージ
ms.date: 10/02/2019
helpviewer_keywords:
- specifiers [C++], type
- integral types, storage
- storage [C++], types
- floating-point numbers, storage
- type specifiers [C++], sizes
- arithmetic operations [C++], types
- int data type
- short data type
- signed types [C++], storage
- long double keyword [C], storage
- long keyword [C]
- double data type, storage
- types [C], arithmetic
- integral types
- data types [C], specifiers
- storing types [C++]
- unsigned types [C++], storage
- data types [C], storage
ms.assetid: bd1f33c1-c6b9-4558-8a72-afb21aef3318
ms.openlocfilehash: 973866a912b694510d587df765ac8dd54176638e
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87211672"
---
# <a name="storage-of-basic-types"></a>基本型のストレージ

次の表は、各基本型に関連付けられたストレージをまとめたものです。

## <a name="sizes-of-fundamental-types"></a>基本型のサイズ

|種類|記憶域|
|----------|-------------|
|**`char`** , **`unsigned char`** , **`signed char`**|1 バイト|
|**`short`** , **`unsigned short`**|2 バイト|
|**`int`** , **`unsigned int`**|4 バイト|
|**`long`** , **`unsigned long`**|4 バイト|
|**`long long`** , **`unsigned long long`**|8 バイト|
|**`float`**|4 バイト|
|**`double`**|8 バイト|
|**`long double`**|8 バイト|

C のデータ型は一般カテゴリに分類されます。 "*整数型*" には、 **`int`** 、 **`char`** 、 **`short`** 、 **`long`** 、および **`long long`** が含まれます。 これらの型は **`signed`** または **`unsigned`** で修飾できます。また、 **`unsigned`** はそれだけで **`unsigned int`** の短縮形として使用できます。 列挙型 ( **`enum`** ) も、ほとんどの目的で整数型として扱われます。 "*浮動小数点型*" には、 **`float`** 、 **`double`** 、および **`long double`** が含まれます。 *数値型*には、すべての浮動小数点型と整数型が含まれます。

## <a name="see-also"></a>関連項目

[宣言と型](../c-language/declarations-and-types.md)
