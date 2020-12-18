---
description: '詳細情報: 符号なし整数型からの変換'
title: 符号なし整数型からの変換
ms.date: 10/02/2019
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
ms.openlocfilehash: bb8f208a323083afeb4b5b88bc8d6514e1f8c99f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97293145"
---
# <a name="conversions-from-unsigned-integral-types"></a>符号なし整数型からの変換

符号なし整数を整数または浮動小数点型に変換する場合、元の値が結果の型で表現できる場合は、値が変更されることはありません。

符号なし整数がより大きいサイズの整数に変換されると、その値はゼロ拡張されます。 より小さいサイズの整数に変換されると、上位ビットは切り捨てられます。 結果は、この例に示すように、結果の型を使用して解釈されます。

```C
unsigned k = 65533;
short j;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

符号なし整数を浮動小数点型に変換する場合、元の値が結果の型で正確に表現できない場合は、結果は次に大きいまたは次に小さい表現可能な値になります。

整数型と浮動小数点型のサイズの詳細については、「[基本型のストレージ](../c-language/storage-of-basic-types.md)」を参照してください。

**Microsoft 固有の仕様**

Microsoft コンパイラでは、 **`unsigned`** (または **`unsigned int`** ) と **`unsigned long`** は区別されますが、同等の型です。 **`unsigned int`** 値の変換は、 **`unsigned long`** の変換と同様に実行されます。

**Microsoft 固有の仕様はここまで**

次の表は、符号なし整数型からの変換をまとめたものです。

## <a name="table-of-conversions-from-unsigned-integral-types"></a>符号なし整数型からの変換の表

|From|終了|メソッド|
|----------|--------|------------|
|**`unsigned char`**|**`char`**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**`unsigned char`**|**`short`**|ゼロ拡張。|
|**`unsigned char`**|**`long`**|ゼロ拡張。|
|**`unsigned char`**|**`long long`**|ゼロ拡張。|
|**`unsigned char`**|**`unsigned short`**|ゼロ拡張。|
|**`unsigned char`**|**`unsigned long`**|ゼロ拡張。|
|**`unsigned char`**|**`unsigned long long`**|ゼロ拡張。|
|**`unsigned char`**|**`float`**|**`long`** への変換、 **`long`** を **`float`** に変換|
|**`unsigned char`**|**`double`**|**`long`** への変換、 **`long`** を **`double`** に変換|
|**`unsigned char`**|**`long double`**|**`long`** への変換、 **`long`** を **`double`** に変換|
|**`unsigned short`**|**`char`**|下位バイトを維持。|
|**`unsigned short`**|**`short`**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**`unsigned short`**|**`long`**|ゼロ拡張。|
|**`unsigned short`**|**`long long`**|ゼロ拡張。|
|**`unsigned short`**|**`unsigned char`**|下位バイトを維持。|
|**`unsigned short`**|**`unsigned long`**|ゼロ拡張。|
|**`unsigned short`**|**`unsigned long long`**|ゼロ拡張。|
|**`unsigned short`**|**`float`**|**`long`** への変換、 **`long`** を **`float`** に変換|
|**`unsigned short`**|**`double`**|**`long`** への変換、 **`long`** を **`double`** に変換|
|**`unsigned short`**|**`long double`**|**`long`** への変換、 **`long`** を **`double`** に変換|
|**`unsigned long`**|**`char`**|下位バイトを維持。|
|**`unsigned long`**|**`short`**|下位ワードを維持。|
|**`unsigned long`**|**`long`**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**`unsigned long`**|**`long long`**|ゼロ拡張。|
|**`unsigned long`**|**`unsigned char`**|下位バイトを維持。|
|**`unsigned long`**|**`unsigned short`**|下位ワードを維持。|
|**`unsigned long`**|**`unsigned long long`**|ゼロ拡張。|
|**`unsigned long`**|**`float`**|**`long`** への変換、 **`long`** を **`float`** に変換|
|**`unsigned long`**|**`double`**|**`double`** への直接変換|
|**`unsigned long`**|**`long double`**|**`long`** への変換、 **`long`** を **`double`** に変換|
|**`unsigned long long`**|**`char`**|下位バイトを維持。|
|**`unsigned long long`**|**`short`**|下位ワードを維持。|
|**`unsigned long long`**|**`long`**|下位 dword を維持。|
|**`unsigned long long`**|**`long long`**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**`unsigned long long`**|**`unsigned char`**|下位バイトを維持。|
|**`unsigned long long`**|**`unsigned short`**|下位ワードを維持。|
|**`unsigned long long`**|**`unsigned long`**|下位 dword を維持。|
|**`unsigned long long`**|**`float`**|**`long`** への変換、 **`long`** を **`float`** に変換|
|**`unsigned long long`**|**`double`**|**`double`** への直接変換|
|**`unsigned long long`**|**`long double`**|**`long`** への変換、 **`long`** を **`double`** に変換|

## <a name="see-also"></a>関連項目

[代入変換](../c-language/assignment-conversions.md)
