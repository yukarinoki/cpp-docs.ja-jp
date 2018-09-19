---
title: 符号なし整数型からの変換 | Microsoft Docs
ms.custom: ''
ms.date: 01/29/2018
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integers, converting
- type casts, involving integers
- data type conversion [C++], signed and unsigned integers
- type conversion [C++], signed and unsigned integers
- integral conversions, from unsigned
ms.assetid: 60fb7e10-bff9-4a13-8a48-e19f25a36a02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 38ef2c16c92322ae54dcc6dd7d577268daf74831
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058277"
---
# <a name="conversions-from-unsigned-integral-types"></a>Conversions from Unsigned Integral Types (符号なし整数型からの変換)

符号なし整数は、上位ビットを切り捨てることによって短い符号なしまたは符号付き整数に変換されます。または、ゼロ拡張によって長い符号なしまたは符号付き整数に変換されます (「[符号なし整数型からの変換](#_clang_table_4..3)」表をご覧ください)。

整数型の値がサイズの小さい符号付き整数に下位変換されるか、符号なし整数が対応する符号付き整数に変換される場合、新しい型で表すことができるときには、値は変更されません。 ただし、次の例のように、符号ビットが設定される場合は、表される値が変更されます。

```C
int j;
unsigned short k = 65533;

j = k;
printf_s( "%hd\n", j );   // Prints -3
```

値を表すことができない場合、結果は実装定義になります。 Microsoft C コンパイラの整数の下位変換処理については、「[型キャスト変換](../c-language/type-cast-conversions.md)」をご覧ください。 整数変換や整数の型キャストによっても、同じ動作が発生します。

符号なしの値は、その値を保持したまま変換され、直接 C 言語で表現できません。唯一の例外は **unsigned long** から **float** への変換で、最大では下位ビットが失われます。 それ以外の場合は、符号付きでも符号なしでも、値は維持されます。 整数型の値を浮動小数点型に変換するときに、値が表せる範囲を超えている場合の結果は、未定義になります。 整数型と浮動小数点型の範囲については、「[基本型の格納](../c-language/storage-of-basic-types.md)」をご覧ください。

次の表は、符号なし整数型からの変換をまとめたものです。

## <a name="conversions-from-unsigned-integral-types"></a>符号なし整数型からの変換

|From|終了|メソッド|
|----------|--------|------------|
|**unsigned char**|**char**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**unsigned char**|**short**|ゼロ拡張。|
|**unsigned char**|**long**|ゼロ拡張。|
|**unsigned char**|**unsigned short**|ゼロ拡張。|
|**unsigned char**|**unsigned long**|ゼロ拡張。|
|**unsigned char**|**float**|**long** への変換、**long** から **float** への変換。|
|**unsigned char**|**double**|**long** への変換、**long** から **double** への変換。|
|**unsigned char**|**long double**|**long** への変換、**long** から **double** への変換。|
|**unsigned short**|**char**|下位バイトを維持。|
|**unsigned short**|**short**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**unsigned short**|**long**|ゼロ拡張。|
|**unsigned short**|**unsigned char**|下位バイトを維持。|
|**unsigned short**|**unsigned long**|ゼロ拡張。|
|**unsigned short**|**float**|**long** への変換、**long** から **float** への変換。|
|**unsigned short**|**double**|**long** への変換、**long** から **double** への変換。|
|**unsigned short**|**long double**|**long** への変換、**long** から **double** への変換。|
|**unsigned long**|**char**|下位バイトを維持。|
|**unsigned long**|**short**|下位ワードを維持。|
|**unsigned long**|**long**|ビット パターンを維持、上位ビットが符号ビットになる。|
|**unsigned long**|**unsigned char**|下位バイトを維持。|
|**unsigned long**|**unsigned short**|下位ワードを維持。|
|**unsigned long**|**float**|**long** への変換、**long** から **float** への変換。|
|**unsigned long**|**double**|**double** への直接変換。|
|**unsigned long**|**long double**|**long** への変換、**long** から **double** への変換。|

**Microsoft 固有の仕様**

Microsoft C コンパイラの場合、**unsigned int** 型は **unsigned long** 型と同等です。 **unsigned int** 値の変換は、**unsigned long** の変換と同様に実行されます。 **unsigned long** 値から **float** への変換は、変換されている値が正の符号付き **long** の最大値より大きい場合は、正確ではありません。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[代入の変換](../c-language/assignment-conversions.md)
