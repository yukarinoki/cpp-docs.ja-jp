---
title: データ型指定子と同等物 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b7380fa654ba7e886800d784966b77cb8c9d1dab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32386151"
---
# <a name="data-type-specifiers-and-equivalents"></a>データ型指定子と同等物
このブックでは、通常、次の表に示す型指定子の短い形式を使用し、長い形式は使用しません。`char` 型は既定で符号付きであることを前提としています。 したがって、このブックでは、`char` は **signed char** と等価です。  
  
### <a name="type-specifiers-and-equivalents"></a>型指定子と同等の形式  
  
|型指定子|同等の形式|  
|--------------------|---------------------|  
|**signed char**1|**char**|  
|**signed int**|**signed**、**int**|  
|**signed short int**|**short**、**signed short**|  
|**signed long int**|**long**、**signed long**|  
|**unsigned char**|—|  
|**unsigned int**|**unsigned**|  
|**unsigned short int**|**unsigned short**|  
|**unsigned long int**|**unsigned long**|  
|**float**|—|  
|**long double**2|—|  
  
 1   **char** 型を既定で unsigned にすると (/J コンパイラ オプションを指定)、**signed char** を **char** と短縮できません。  
  
 2   32 ビットまたは 64 ビット オペレーティング システムでは、Microsoft C コンパイラは **long double** を **double** 型にマップします。  
  
 **Microsoft 固有の仕様**  
  
 /J コンパイラ オプションを指定して、既定の **char** 型を符号付きから符号なしに変更できます。 このオプションが有効になっている場合、**char** は **unsigned char** と同じ意味であり、符号付き文字の値を宣言するには **signed** キーワードを使用する必要があります。 **char** 値を明示的に signed 宣言すると、/J オプションは適用されません。**int** 型に上位変換すると、値が符号拡張されます。 **char** 型は、**int** 型に上位変換するとゼロ拡張されます。  
  
 **Microsoft 固有の仕様はここまで**  
  
## <a name="see-also"></a>参照  
 [C 型指定子](../c-language/c-type-specifiers.md)