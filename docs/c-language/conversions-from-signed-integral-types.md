---
title: 符号付き整数型からの変換
ms.date: 10/02/2019
helpviewer_keywords:
- integral conversions, from signed
- integers, converting
- conversions [C++], integral
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
ms.assetid: 5eea32f8-8b14-413d-acac-c063b3d118d7
ms.openlocfilehash: d41d2fd205a87f9f2be2179ffd8e38256a96e4f7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87226478"
---
# <a name="conversions-from-signed-integral-types"></a>符号付き整数型からの変換

符号付き整数を整数または浮動小数点型に変換する場合、元の値が結果の型で表現できる場合は、値が変更されることはありません。

符号付き整数がより大きいサイズの整数に変換されると、その値は符号拡張されます。 より小さいサイズの整数に変換されると、上位ビットは切り捨てられます。 結果は、この例に示すように、結果の型を使用して解釈されます。

```C
int i = -3;
unsigned short u;

u = i;
printf_s( "%hu\n", u );  // Prints 65533
```

符号付き整数を浮動小数点型に変換する場合、元の値が結果の型で正確に表現できない場合は、結果は次に大きいまたは次に小さい表現可能な値になります。

整数型と浮動小数点型のサイズの詳細については、「[基本型のストレージ](../c-language/storage-of-basic-types.md)」を参照してください。

次の表は、符号付き整数型からの変換をまとめたものです。 **`char`** 型は既定では符号付きであると仮定されています。 コンパイル時オプションを使用して **`char`** 型の既定を unsigned (符号なし) に変更すると、この表の変換の代わりに、「[符号なし整数型からの変換](../c-language/conversions-from-unsigned-integral-types.md)」の表で示されている **`unsigned char`** 型の変換が適用されます。

**Microsoft 固有の仕様**

Microsoft コンパイラでは、 **`int`** と **`long`** は区別されますが、同等の型です。 **`int`** 値の変換は、 **`long`** の変換と同様に実行されます。

**Microsoft 固有の仕様はここまで**

## <a name="table-of-conversions-from-signed-integral-types"></a>符号付き整数型からの変換の表

|From|終了|メソッド|
|----------|--------|------------|
|**`char`** <sup>1</sup>|**`short`**|符号拡張。|
|**`char`**|**`long`**|符号拡張。|
|**`char`**|**`long long`**|符号拡張。|
|**`char`**|**`unsigned char`**|パターンを維持、上位ビットは符号ビットとしての機能を失う。|
|**`char`**|**`unsigned short`**|**`short`** への符号拡張、 **`short`** から **`unsigned short`** への変換|
|**`char`**|**`unsigned long`**|**`long`** への符号拡張、 **`long`** から **`unsigned long`** への変換|
|**`char`**|**`unsigned long long`**|**`long long`** への符号拡張、 **`long long`** から **`unsigned long long`** への変換|
|**`char`**|**`float`**|**`long`** への符号拡張、 **`long`** から **`float`** への変換|
|**`char`**|**`double`**|**`long`** への符号拡張、 **`long`** から **`double`** への変換|
|**`char`**|**`long double`**|**`long`** への符号拡張、 **`long`** から **`double`** への変換|
|**`short`**|**`char`**|下位バイトを維持。|
|**`short`**|**`long`**|符号拡張。|
|**`short`**|**`long long`**|符号拡張。|
|**`short`**|**`unsigned char`**|下位バイトを維持。|
|**`short`**|**`unsigned short`**|ビット パターンを維持、上位ビットは符号ビットとしての機能を失う。|
|**`short`**|**`unsigned long`**|**`long`** への符号拡張、 **`long`** から **`unsigned long`** への変換|
|**`short`**|**`unsigned long long`**|**`long long`** への符号拡張、 **`long long`** から **`unsigned long long`** への変換|
|**`short`**|**`float`**|**`long`** への符号拡張、 **`long`** から **`float`** への変換|
|**`short`**|**`double`**|**`long`** への符号拡張、 **`long`** から **`double`** への変換|
|**`short`**|**`long double`**|**`long`** への符号拡張、 **`long`** から **`double`** への変換|
|**`long`**|**`char`**|下位バイトを維持。|
|**`long`**|**`short`**|下位ワードを維持。|
|**`long`**|**`long long`**|符号拡張。|
|**`long`**|**`unsigned char`**|下位バイトを維持。|
|**`long`**|**`unsigned short`**|下位ワードを維持。|
|**`long`**|**`unsigned long`**|ビット パターンを維持、上位ビットは符号ビットとしての機能を失う。|
|**`long`**|**`unsigned long long`**|**`long long`** への符号拡張、 **`long long`** から **`unsigned long long`** への変換|
|**`long`**|**`float`**|**`float`** として表される。 **`long`** を正確に表すことができない場合、精度が低下する場合があります。|
|**`long`**|**`double`**|**`double`** として表される。 **`long`** を **`double`** として正確に表すことができない場合、精度が低下する場合があります。|
|**`long`**|**`long double`**|**`double`** として表される。 **`long`** を **`double`** として正確に表すことができない場合、精度が低下する場合があります。|
|**`long long`**|**`char`**|下位バイトを維持。|
|**`long long`**|**`short`**|下位ワードを維持。|
|**`long long`**|**`long`**|下位 dword を維持。|
|**`long long`**|**`unsigned char`**|下位バイトを維持。|
|**`long long`**|**`unsigned short`**|下位ワードを維持。|
|**`long long`**|**`unsigned long`**|下位 dword を維持。|
|**`long long`**|**`unsigned long long`**|ビット パターンを維持、上位ビットは符号ビットとしての機能を失う。|
|**`long long`**|**`float`**|**`float`** として表される。 **`long long`** を正確に表すことができない場合、精度が低下する場合があります。|
|**`long long`**|**`double`**|**`double`** として表される。 **`long long`** を **`double`** として正確に表すことができない場合、精度が低下する場合があります。|
|**`long long`**|**`long double`**|**`double`** として表される。 **`long long`** を **`double`** として正確に表すことができない場合、精度が低下する場合があります。|

<sup>1</sup> **`char`** のすべてのエントリでは、 **`char`** 型は既定では符号付きであると想定されています。

## <a name="see-also"></a>関連項目

[代入変換](../c-language/assignment-conversions.md)
