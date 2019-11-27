---
title: データ型の範囲
ms.date: 05/07/2019
helpviewer_keywords:
- float keyword [C++]
- char keyword [C++]
- unsigned long
- __wchar_t keyword [C++]
- unsigned short int [C++]
- enum keyword [C++]
- unsigned char keyword [C++]
- integer data type [C++], data type ranges
- int data type
- data types [C++], ranges
- unsigned int [C++]
- short data type
- short int data
- signed types [C++], data type ranges
- long long keyword [C++]
- long double keyword [C++]
- double data type [C++], data type ranges
- signed short int [C++]
- unsigned short
- sized integer types
- signed int [C++]
- signed long int [C++]
- signed char keyword [C++]
- wchar_t keyword [C++]
- long keyword [C++]
- ranges [C++]
- unsigned types [C++], data type ranges
- floating-point numbers [C++]
- data type ranges
- ranges [C++], data types
- long int keyword [C++]
- unsigned long int [C++]
ms.assetid: 3691ceca-05fb-4b82-b1ae-5c4618cda91a
ms.openlocfilehash: 9eed9b35df6f5a970d05b09a604507df719345db
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65222177"
---
# <a name="data-type-ranges"></a>データ型の範囲

Microsoft C++ 32 ビットおよび 64 ビット コンパイラは、この記事の後半で、テーブル内の型を認識します。

- `int` (`unsigned int`)

- `__int8` (`unsigned __int8`)

- `__int16` (`unsigned __int16`)

- `__int32` (`unsigned __int32`)

- `__int64` (`unsigned __int64`)

- `short` (`unsigned short`)

- `long` (`unsigned long`)

- `long` `long` (`unsigned long long`)

データ型の名前が 2 つのアンダースコア (`__`) で始まる場合、その型は非標準です。

次の表で指定している範囲にはその最大値と最小値も含まれます。

|型の名前|バイト|その他の名前|値の範囲|
|---------------|-----------|-----------------|---------------------|
|**int**|4|**signed**|-2,147,483,648 ～ 2,147,483,647|
|**unsigned int**|4|**unsigned**|0 ～ 4,294,967,295|
|**__int8**|1|**char**|-128 ～ 127|
|**unsigned __int8**|1|**unsigned char**|0 ～ 255|
|**__int16**|2|**short**、 **short int**、**signed short int**|-32,768 ～ 32,767|
|**unsigned __int16**|2|**unsigned short**、**unsigned short int**|0 ～ 65,535|
|**__int32**|4|**signed**、 **signed int**、 **int**|-2,147,483,648 ～ 2,147,483,647|
|**unsigned __int32**|4|**unsigned**、**unsigned int**|0 ～ 4,294,967,295|
|**__int64**|8|**long**、 **signed long long**|-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807|
|**unsigned __int64**|8|**unsigned long long**|0 ～ 18,446,744,073,709,551,615|
|**bool**|1|none|**false**または**は true。**|
|**char**|1|none|既定では、128 ~ 127<br /><br /> [/J](../build/reference/j-default-char-type-is-unsigned.md)を使用してコンパイルするときは 0 〜 255|
|**signed char**|1|none|-128 ～ 127|
|**unsigned char**|1|none|0 ～ 255|
|**short**|2|**short int**、**signed short int**|-32,768 ～ 32,767|
|**unsigned short**|2|**unsigned short int**|0 ～ 65,535|
|**long**|4|**long int**、 **signed long int**|-2,147,483,648 ～ 2,147,483,647|
|**unsigned long**|4|**unsigned long int**|0 ～ 4,294,967,295|
|**long long**|8|none (と同等では **_ _int64**)|-9,223,372,036,854,775,808 から 9,223,372,036,854,775,807|
|**unsigned long long**|8|none (と同等では**unsigned _ _int64**)|0 ～ 18,446,744,073,709,551,615|
|**enum**|可変|none| |
|**float**|4|none|3.4E +/- 38 (7 桁)|
|**double**|8|none|1.7E +/- 308 (15 桁)|
|**long double**|同じ**double**|none|同じ**double**|
|**wchar_t**|2|**__wchar_t**|0 ～ 65,535|

使用方法に応じて、変数の **_ _wchar_t**ワイド文字型またはマルチバイト文字の種類のいずれかを指定します。 ワイド文字型の定数を指定するには、文字または文字列定数の前に `L` のプレフィックスを使用します。

**signed**と**unsigned**修飾子を除く任意の整数型で使用できるは**bool**します。 なお**char**、 **signed char**、および**unsigned char**オーバーロードやテンプレートなどのメカニズムの目的では 3 つの型。

**int**と**unsigned int**型のサイズは 4 バイトがあります。 ただし、移植可能なコードは、のサイズに依存する必要がありますしない**int**標準の言語は、この実装に固有であるためです。

Visual Studio での C/C++ では、サイズが設定された整数型をサポートしています。 詳細については、「[__int8、\__int16、\__int32、\__int64](../cpp/int8-int16-int32-int64.md)」および「[整数の制限](../cpp/integer-limits.md)」を参照してください。

型ごとのサイズの制限の詳細については、「[基本的な型](../cpp/fundamental-types-cpp.md)」を参照してください。

列挙型の範囲は、言語コンテキストと指定したコンパイラ フラグによって異なります。 詳細については、「 [C 列挙体の宣言](../c-language/c-enumeration-declarations.md) 」および「 [列挙型](../cpp/enumerations-cpp.md)」を参照してください。

## <a name="see-also"></a>関連項目

[キーワード](../cpp/keywords-cpp.md)<br/>
[基本的な型](../cpp/fundamental-types-cpp.md)
