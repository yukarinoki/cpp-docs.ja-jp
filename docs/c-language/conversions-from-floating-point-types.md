---
title: 浮動小数点型からの変換
ms.date: 10/02/2019
helpviewer_keywords:
- converting floating point
- floating-point conversion
ms.assetid: 96804c8e-fa3b-4742-9006-0082ed9e57f2
ms.openlocfilehash: c2f7c25015b36545f969796a1f85d355d715427a
ms.sourcegitcommit: c51b2c665849479fa995bc3323a22ebe79d9d7ce
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/07/2019
ms.locfileid: "71998715"
---
# <a name="conversions-from-floating-point-types"></a>浮動小数点型からの変換

別の浮動小数点型に変換された浮動小数点値では、元の値が結果の型で正確に表現できる場合、値が変更されることはありません。 元の値が数値であっても、正確に表現できない場合、結果は次に大きいまたは次に小さい表現可能な値のいずれかになります。 浮動小数点型の範囲については、「[浮動小数点定数の制限](../c-language/limits-on-floating-point-constants.md)」を参照してください。

整数型に変換される浮動小数点値は、まず小数値を破棄することによって切り捨てられます。 この切り捨てられた値が結果の型で表現できる場合、結果はその値である必要があります。 表現できない場合、結果の値は未定義になります。

**Microsoft 固有の仕様**

Microsoft コンパイラでは **float** 値に対して IEEE-754 binary32 表現が使用され、**long double** および **double** に対して binary64 表現が使用されます。 **long double** と **double** では同じ表現が使用されているため、範囲と精度は同じです。

コンパイラにより **double** または **long double** 浮動小数点が **float** に変換されると、浮動小数点環境コントロールに従って結果が丸められます。これは、既定では "最近接偶数への丸め" になります。 数値が大きすぎるか小さすぎるために数値の **float** 値として表現することができない場合、変換結果は元の値の符号に応じて正または負の無限大になり、オーバーフロー例外が発生します (有効になっている場合)。

整数型に変換する場合、**long** より小さい型への変換の結果は、その値を **long** に変換し、それから結果の型に変換した結果になります。

少なくとも **long** と同じ大きさの整数型に変換する場合、大きすぎるか小さすぎるために結果の型で表現できない値を変換すると、次のいずれかの値が返される可能性があります。

- 結果は *sentinel 値*になる可能性があります。これは、0 から最も遠い表現可能な値です。 符号付きの型の場合、これは最小の表現可能な値 (0x800...0) です。 符号なしの型の場合、これは最大の表現可能な値 (0xFF...F) です。

- 結果は*飽和*になる可能性があります。この場合、大きすぎて表現できない値が表現可能な最大の値に変換され、小さすぎて表現できない値が表現可能な最小の値に変換されます。 これら 2 つの値のいずれかが、sentinel 値としても使用されます。

- **unsigned long** または **unsigned long long** への変換では、範囲外の値を変換した結果は、表現可能な最大または最小の値以外の値になる可能性があります。 結果が sentinel または飽和値であるかどうかは、コンパイラ オプションとターゲット アーキテクチャによって異なります。 将来のコンパイラ リリースでは、飽和または sentinel 値が代わりに返される可能性があります。

**Microsoft 固有の仕様はここまで**

次の表は、浮動小数点型から変換をまとめたものです。

## <a name="table-of-conversions-from-floating-point-types"></a>浮動小数点型からの変換の表

|From|終了|メソッド|
|----------|--------|------------|
|**float**|**char**|**long** への変換、**long** から **char** への変換|
|**float**|**short**|**long** への変換、**long** から **short** への変換|
|**float**|**int**|小数点で切り捨てます。 結果が **int** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**long**|小数点で切り捨てます。 結果が **long** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**long long**|小数点で切り捨てます。 結果が **long long** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**unsigned char**|**long** への変換、**long** から **unsigned char** への変換|
|**float**|**unsigned short**|**long** への変換、**long** から **unsigned short** への変換|
|**float**|**unsigned**|小数点で切り捨てます。 結果が **unsigned** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**unsigned long**|小数点で切り捨てます。 結果が **unsigned long** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**unsigned long long**|小数点で切り捨てます。 結果が **unsigned long long** で表すには大きすぎる場合、結果は未定義になります。|
|**float**|**double**|**double** として表される。|
|**float**|**long double**|**long double** として表される。|
|**double**|**char**|**float** への変換、**float** から **char** への変換|
|**double**|**short**|**float** への変換、**float** から **short** への変換|
|**double**|**int**|小数点で切り捨てます。 結果が **int** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**long**|小数点で切り捨てます。 結果が **long** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**unsigned char**|**long** への変換、**long** から **unsigned char** への変換|
|**double**|**unsigned short**|**long** への変換、**long** から **unsigned short** への変換|
|**double**|**unsigned**|小数点で切り捨てます。 結果が **unsigned** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**unsigned long**|小数点で切り捨てます。 結果が **unsigned long** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**unsigned long long**|小数点で切り捨てます。 結果が **unsigned long long** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**float**|**float** として表します。 **double** 値を **float** 型で正確に表すことができない場合、精度が低下します。 値が **float** で表すには大きすぎる場合、結果は未定義になります。|
|**double**|**long double**|**long double** 値は **double** として扱われます。|

**long double** からの変換は **double** からの変換と同じ方法に従います。

## <a name="see-also"></a>関連項目

[代入変換](../c-language/assignment-conversions.md)
