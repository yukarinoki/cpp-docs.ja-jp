---
description: '詳細情報: 通常の算術変換'
title: 通常の算術変換
ms.date: 11/04/2016
helpviewer_keywords:
- arithmetic conversions [C++]
- type conversion [C++], arithmetic
- operators [C], arithmetic conversions
- data type conversion [C++], arithmetic
- conversions [C++], arithmetic
- arithmetic operators [C++], type conversions
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
ms.openlocfilehash: 443d61b3ff295431a5c1507886cb0821a1f5b205
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198896"
---
# <a name="usual-arithmetic-conversions"></a>通常の算術変換

ほとんどの C 演算子は、式のオペランドを共通型に取り込むか、コンピューター操作に使用される整数のサイズに short 値を拡張する型変換を実行します。 C 演算子によって実行される変換は、特定の演算子およびオペランドの型によって異なります。 ただし、多くの演算子は、整数型および浮動小数点型のオペランドに対して同様の変換を実行します。 これらの変換は "算術変換" と呼ばれます。 オペランド値を互換性のある型に変換しても、その値は変更されません。

以下にまとめた算術変換は、"通常の算術変換" と呼ばれます。 これらの手順は、数値型を要求する二項演算子の場合にのみ適用されます。 目的は、結果の型でもある共通型を導入することです。 実際にどの変換が行われるかを確認するために、コンパイラは式のバイナリ操作に次のアルゴリズムを適用します。 次の手順は優先順ではありません。

1. どちらかのオペランドが **`long double`** 型の場合、もう一方のオペランドは **`long double`** 型に変換されます。

1. 上の条件が満たされず、どちらかのオペランドが **`double`** 型である場合、もう一方のオペランドは **`double`** 型に変換されます。

1. 上の 2 つの条件が満たされず、どちらかのオペランドが **`float`** 型の場合、もう一方のオペランドは **`float`** 型に変換されます。

1. 上の 3 つの条件が満たされない場合 (どのオペランドも浮動小数点型でない場合)、オペランドに対して次のように整数変換が実行されます。

   - どちらかのオペランドが **`unsigned long`** 型の場合、もう一方のオペランドは **`unsigned long`** 型に変換されます。

   - 上の条件が満たされず、どちらかのオペランドが **`long`** 型で、もう一方が **`unsigned int`** 型である場合、両方のオペランドが **`unsigned long`** 型に変換されます。

   - 上の 2 つの条件が満たされず、どちらかのオペランドが **`long`** 型である場合、もう一方のオペランドは **`long`** 型に変換されます。

   - 上の 3 つの条件が満たされず、どちらかのオペランドが **`unsigned int`** 型である場合、もう一方のオペランドは **`unsigned int`** 型に変換されます。

   - 上記いずれの条件にも一致しない場合、両方のオペランドが **`int`** 型に変換されます。

次のコードは、これらの変換規則を示します。

```
float   fVal;
double  dVal;
int   iVal;
unsigned long ulVal;

dVal = iVal * ulVal; /* iVal converted to unsigned long
                      * Uses step 4.
                      * Result of multiplication converted to double
                      */
dVal = ulVal + fVal; /* ulVal converted to float
                      * Uses step 3.
                      * Result of addition converted to double
                      */
```

## <a name="see-also"></a>関連項目

[C 演算子](../c-language/c-operators.md)
