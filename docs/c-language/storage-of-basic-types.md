---
title: 基本型の格納
ms.date: 11/04/2016
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
ms.openlocfilehash: 51b67b375cf7a4608d3080e5922cabbf3135ddfe
ms.sourcegitcommit: f4be868c0d1d78e550fba105d4d3c993743a1f4b
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/12/2019
ms.locfileid: "56152249"
---
# <a name="storage-of-basic-types"></a>基本型の格納

次の表は、各基本型に関連付けられたストレージをまとめたものです。

### <a name="sizes-of-fundamental-types"></a>基本型のサイズ

|型|記憶域|
|----------|-------------|
|`char`, `unsigned char`, **signed char**|1 バイト|
|**short**, **unsigned short**|2 バイト|
|`int`、 `unsigned int`|4 バイト|
|**long**, `unsigned long`|4 バイト|
|**float**|4 バイト|
|**double**|8 バイト|
|`long double`|8 バイト|

C のデータ型は一般カテゴリに分類されます。 "整数型" には、`char`、`int`、**short**、**long**、**signed**、`unsigned`、および `enum` が含まれます。 "浮動小数点型" には、**float**、**double**、および `long double` が含まれます。 "数値型" には、すべての浮動小数点型と整数型が含まれます。

## <a name="see-also"></a>関連項目

[宣言と型](../c-language/declarations-and-types.md)
