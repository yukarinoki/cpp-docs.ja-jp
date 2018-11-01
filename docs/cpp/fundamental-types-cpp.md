---
title: 基本型 (C++)
ms.date: 11/04/2016
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- double_cpp
- float_cpp
- int_cpp
- long_cpp
- long_double_cpp
- short_cpp
- signed_cpp
- unsigned_cpp
- unsigned_int_cpp
- wchar_t_cpp
helpviewer_keywords:
- specifiers [C++], type
- float keyword [C++]
- char keyword [C++]
- __wchar_t keyword [C++]
- signed types [C++], summary of data types
- Integer data type [C++], C++ data types
- arithmetic operations [C++], types
- int data type
- unsigned types [C++], summary of data types
- short data type [C++]
- double data type [C++], summary of types
- long long keyword [C++]
- long double keyword [C++]
- unsigned types [C++]
- signed types [C++]
- void keyword [C++]
- storage [C++], basic type
- integral types, C++
- wchar_t keyword [C++]
- floating-point numbers [C++], C++ data types
- long keyword [C++]
- type specifiers [C++]
- integral types
- long keyword [C++], C++ data types
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: f4af392ed559349b0e49fd26f3ecb4406a70b74b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50601371"
---
# <a name="fundamental-types--c"></a>基本型 (C++)

C++ の基本的な型は、整数、浮動小数点、および void の 3 つのカテゴリに分類されます。 整数型は整数を処理できます。 浮動小数点型は小数部分を含む可能性がある値を指定することができます。

[void](../cpp/void-cpp.md) 型は一連の空の値を示します。 型の変数**void**を指定できます: 値を返さない関数を宣言するには、主に使用されますか、型指定されたデータに型指定されていない、または任意のジェネリック ポインターを宣言しません。 任意の式を明示的に変換または型にキャスト**void**します。 ただし、このような式は次の用途に制限されています。

- 式ステートメント (詳細については、「 [式](../cpp/expressions-cpp.md)」を参照)。

- コンマ演算子の左のオペランド (詳細については、「 [コンマ演算子](../cpp/comma-operator.md) 」を参照)。

- 条件演算子の 2 番目または 3 番目のオペランド (`? :`)。 (詳細については、「 [条件演算子を含む式](../cpp/conditional-operator-q.md) 」を参照)。

型のサイズに適用される制限を次の表に示します。 これらの制限は、Microsoft の実装に依存しません。

### <a name="fundamental-types-of-the-c-language"></a>C++ 言語の基本型

|カテゴリ|型|目次|
|--------------|----------|--------------|
|整数型|**char**|型**char**は通常、基本実行文字セットのメンバーを含む整数型、既定では、これは、Microsoft C では ASCII です。<br /><br /> C++ コンパイラが型の変数を扱う**char**、 **char を署名**、および**unsigned char**として別の型を持ちます。 型の変数**char**に昇格される**int**型している場合、 **char を署名**既定では、/J コンパイル オプションを使用しない場合。 ここでは型として扱われます**unsigned char**に昇格**int**符号拡張なし。|
||**bool**|型**bool**する 2 つの値のいずれかの整数型は、 **true**または**false**します。 そのサイズは、指定されていません。|
||**short**|型**short int** (または単に**短い**) 型のサイズ以上である整数型は、 **char**、および型のサイズ以下**int**します。<br /><br /> 型のオブジェクト**短い**として宣言できます**つまり署名**または**unsigned short**します。 **つまり署名**のシノニムです**短い**します。|
||**int**|型**int**型のサイズ以上である整数型は、 **short int**、およびよりもより短い、または型のサイズと等しく**長い**します。<br /><br /> 型のオブジェクト**int**として宣言できます**int を署名**または**符号なし int**します。**Int を署名**のシノニムです**int**します。|
||**_ _int8**、 **_ _int16**、 **_ _int32**、 **_ _int64**|サイズが設定された整数 `__int n`( `n` は整数変数のビット単位のサイズ) **_ _int8**、 **_ _int16**、 **_ _int32**と **_ _int64**は Microsoft 固有キーワードです。 すべての種類は、すべてのアーキテクチャで使用できます。 (**__int128**はサポートされていません)。|
||**long**|型**長い**(または**long int**) 型のサイズ以上である整数型は、 **int**します。<br /><br /> 型のオブジェクト**長い**として宣言できます**時間の長い署名**または**unsigned long**します。 **時間の長い署名**のシノニムです**長い**します。|
||**long long**|符号なしのよりも大きい**長い**します。<br /><br /> 型のオブジェクト**long**として宣言できます**long long 型署名**または**unsigned long long 型**します。 **long long 型署名**のシノニムです**long**します。|
||**wchar_t**、 **_ _wchar_t**|型の変数**wchar_t**はワイド文字またはマルチバイト文字型を指定します。 既定では、 **wchar_t**のネイティブな型ですが、使用できる[/Zc:wchar_t-](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)させる**wchar_t**の typedef **unsigned short**します。 **_ _Wchar_t**型は、ネイティブの Microsoft 固有のシノニムです**wchar_t**型。<br /><br /> ワイド文字型を指定するには、文字や文字列リテラルの前に L のプレフィックスを使用します。|
|浮動小数点数|**float**|型**float**は最小の浮動小数点型。|
||**double**|型**二重**を超える浮動小数点型または型に等しい**float**がよりも短いか型のサイズに等しい**long double**します。<br /><br /> Microsoft 固有: の表現**long double**と**二重**と同じです。 ただし、 **long double**と**二重**は個別の型。|
||**long double**|型**long double**が浮動小数点型よりも大きいですまたは型に等しい**二重**します。|

**Microsoft 固有の仕様**

次の表は、Microsoft C++ において基本的な型に必要とされるストレージの量の一覧です。

### <a name="sizes-of-fundamental-types"></a>基本型のサイズ

|型|サイズ|
|----------|----------|
|**bool**、 **char**、 **unsigned char**、 **char を署名**、 **_ _int8**|1 バイト|
|**_ _int16**、**短い**、 **unsigned short**、 **wchar_t**、 **_ _wchar_t**|2 バイト|
|**float**、 **_ _int32**、 **int**、**符号なし int**、**長い**、 **unsigned long**|4 バイト|
|**二重**、 **_ _int64**、 **long double**、 **long**|8 バイト|

**Microsoft 固有の仕様はここまで**

型ごとの値の範囲の概要については、「 [データ型の範囲](../cpp/data-type-ranges.md) 」を参照してください。

型変換の詳細については、「 [標準変換](../cpp/standard-conversions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ型の範囲](../cpp/data-type-ranges.md)