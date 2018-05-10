---
title: 基本型の格納 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eafe81dc684300cb7fdf65137c2f7e45010285b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="storage-of-basic-types"></a>基本型の格納
次の表は、各基本型に関連付けられたストレージをまとめたものです。  
  
### <a name="sizes-of-fundamental-types"></a>基本型のサイズ  
  
|型|記憶域|  
|----------|-------------|  
|`char`, `unsigned char`, **signed char**|1 バイト|  
|**short**, **unsigned short**|2 バイト|  
|`int`, `unsigned int`|4 バイト|  
|**long**, `unsigned long`|4 バイト|  
|**float**|4 バイト|  
|**double**|8 バイト|  
|`long double`|8 バイト|  
  
 C のデータ型は一般カテゴリに分類されます。 "整数型" には、`char`、`int`、**short**、**long**、**signed**、`unsigned`、および `enum` が含まれます。 "浮動小数点型" には、**float**、**double**、および `long double` が含まれます。 "数値型" には、すべての浮動小数点型と整数型が含まれます。  
  
## <a name="see-also"></a>参照  
 [宣言と型](../c-language/declarations-and-types.md)