---
description: 詳細については、「組み込み型 (C++)」を参照してください。
title: 組み込み型 (C++)
ms.date: 07/22/2020
f1_keywords:
- __int128_cpp
- __wchar_t_cpp
- char_cpp
- char8_t_cpp
- char16_t_cpp
- char32_t_cpp
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
- long keyword [C++]
- storing types [C++]
- data types [C++], void
ms.assetid: 58b0106a-0406-4b74-a430-7cbd315c0f89
ms.openlocfilehash: 601bd0742002506272ec3da7af448a4bdba96065
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97268744"
---
# <a name="built-in-types-c"></a>組み込み型 (C++)

組み込み型 ( *基本型* とも呼ばれます) は、C++ 言語標準によって指定され、コンパイラに組み込まれています。 組み込み型は、どのヘッダーファイルでも定義されていません。 組み込み型は、 *整数*、 *浮動小数点*、および *void* の3つの主なカテゴリに分類されます。 整数型は整数を表します。 浮動小数点型では、小数部を含む可能性のある値を指定できます。 多くの組み込み型は、コンパイラによって個別の型として扱われます。 ただし、一部の型は *シノニム* であるか、またはコンパイラによって同等の型として扱われます。

## <a name="void-type"></a>void 型

この [`void`](void-cpp.md) 型は、値の空のセットを表します。 型の変数 **`void`** を指定することはできません。 型は主に、値を返さない関数を宣言したり、型指定されてい **`void`** ないデータまたは任意の型のデータへのジェネリックポインターを宣言するために使用されます。 任意の式を明示的に変換するか、型にキャストすることができ **`void`** ます。 ただし、このような式は次の用途に制限されています。

- 式ステートメント (詳細については、「 [式](expressions-cpp.md)」を参照してください)。

- コンマ演算子の左のオペランド (詳細については、「 [コンマ演算子](comma-operator.md)」を参照してください)。

- 条件演算子の 2 番目または 3 番目のオペランド (`? :`)  (詳細については、「 [条件演算子を使用した式](conditional-operator-q.md)」を参照してください)。

## <a name="stdnullptr_t"></a>std:: nullptr_t

キーワード **`nullptr`** は、型の null ポインター定数で、 `std::nullptr_t` 任意の生ポインター型に変換できます。 詳細については、「[`nullptr`](nullptr.md)」を参照してください。

## <a name="boolean-type"></a>ブール型

型には [`bool`](bool-cpp.md) 、[`true`](../cpp/true-cpp.md)または[`false`](../cpp/false-cpp.md)のいずれかの値を指定でき  ます。 型のサイズは **`bool`** 実装固有です。 Microsoft 固有の実装の詳細については、「 [組み込み型のサイズ](#sizes-of-built-in-types) 」を参照してください。

## <a name="character-types"></a>文字型

この **`char`** 型は、基本実行文字セットのメンバーを効率的にエンコードする文字表現型です。 C++ コンパイラは、、、および型の変数を **`char`** **`signed char`** 異なる型で扱い **`unsigned char`** ます。

**Microsoft 固有**: **`char`** **`int`** **`signed char`** [`/J`](../build/reference/j-default-char-type-is-unsigned.md) コンパイルオプションが使用されていない場合、型の変数は既定で as from 型としてに昇格されます。 この場合、型として扱わ **`unsigned char`** れ、符号拡張なしでに上位変換され **`int`** ます。

型の変数 **`wchar_t`** はワイド文字またはマルチバイト文字型です。 **`L`** ワイド文字型を指定するには、文字または文字列リテラルの前にプレフィックスを使用します。

**Microsoft 固有**: 既定では、 **`wchar_t`** はネイティブ型ですが、を使用し [`/Zc:wchar_t-`](../build/reference/zc-wchar-t-wchar-t-is-native-type.md) ての typedef を作成することができ **`wchar_t`** **`unsigned short`** ます。 この **`__wchar_t`** 型は、ネイティブ型の Microsoft 固有のシノニムです **`wchar_t`** 。

この **`char8_t`** 型は、utf-8 文字表現に使用されます。 これはと同じ表現を持ちますが、 **`unsigned char`** コンパイラによって個別の型として扱われます。 **`char8_t`** 型は c++ 20 で新しく追加されたものです。 **Microsoft 固有**: の使用に **`char8_t`**  は、 [`/std:c++latest`](../build/reference/std-specify-language-standard-version.md) コンパイラオプションが必要です。

この **`char16_t`** 型は、utf-16 文字表現に使用されます。 UTF-16 コード単位を表すのに十分な大きさである必要があります。 これは、コンパイラによって個別の型として扱われます。

この **`char32_t`** 型は、32文字表現に使用されます。 32 UTF-8 コード単位を表すのに十分な大きさである必要があります。 これは、コンパイラによって個別の型として扱われます。

## <a name="floating-point-types"></a>浮動小数点型

浮動小数点型では、IEEE-754 表現を使用して、さまざまな大きくなりに対して小数値の近似値を指定します。 次の表は、C++ の浮動小数点型と、浮動小数点型のサイズに対する比較の制限を示しています。 これらの制限は、C++ 標準によって義務付けられており、Microsoft の実装に依存しません。 組み込み浮動小数点型の絶対サイズが標準で指定されていません。

| Type | 内容 |
|--|--|
| **`float`** | 型 **`float`** は、C++ の最小の浮動小数点型です。 |
| **`double`** | 型 **`double`** は、型と同じか、 **`float`** または型のサイズ以下の浮動小数点型です **`long double`** 。 |
| **`long double`** | 型 **`long double`** は、型以上の浮動小数点型です **`double`** 。 |

**Microsoft 固有**: との表現 **`long double`** **`double`** は同じです。 ただし、 **`long double`** と **`double`** は、コンパイラによって個別の型として扱われます。 Microsoft C++ コンパイラは、4 ~ 8 バイトの IEEE-754 浮動小数点表現を使用します。 詳細については、「 [IEEE 浮動小数点表現](../build/ieee-floating-point-representation.md)」を参照してください。

## <a name="integer-types"></a>整数型

**`int`** 型は、既定の基本整数型です。 実装固有の範囲のすべての整数を表すことができます。

*符号付き* 整数表現とは、正と負の両方の値を保持できる値のことです。 既定で使用されるか、または修飾子キーワードが存在する場合に使用され **`signed`** ます。 **`unsigned`** 修飾子キーワードは、負以外の値のみを保持できる *符号なし* の表現を指定します。

サイズ修飾子は、使用する整数表現の幅をビット単位で指定します。 この言語では **`short`** 、、 **`long`** 、および修飾子がサポートされて **`long long`** います。 型は、 **`short`** 少なくとも16ビット幅である必要があります。 型は、 **`long`** 32 ビット幅以上である必要があります。 型は、 **`long long`** 64 ビット幅以上である必要があります。 標準では、整数型の間のサイズの関係を指定します。

`1 == sizeof(char) <= sizeof(short) <= sizeof(int) <= sizeof(long) <= sizeof(long long)`

の実装では、各型の最小サイズ要件とサイズリレーションシップの両方を維持する必要があります。 ただし、実際のサイズは、実装によって異なります。 Microsoft 固有の実装の詳細については、「 [組み込み型のサイズ](#sizes-of-built-in-types) 」を参照してください。

**`int`** **`signed`** 、 **`unsigned`** 、またはサイズ修飾子が指定されている場合、キーワードは省略できます。 修飾子と **`int`** 型 (存在する場合) は、任意の順序で表示される場合があります。 たとえば、 **`short unsigned`** とは **`unsigned int short`** 同じ型を参照します。

### <a name="integer-type-synonyms"></a>整数型のシノニム

次の種類のグループは、コンパイラによってシノニムと見なされます。

- **`short`**, **`short int`**, **`signed short`**, **`signed short int`**

- **`unsigned short`**, **`unsigned short int`**

- **`int`**, **`signed`**, **`signed int`**

- **`unsigned`**, **`unsigned int`**

- **`long`**, **`long int`**, **`signed long`**, **`signed long int`**

- **`unsigned long`**, **`unsigned long int`**

- **`long long`**, **`long long int`**, **`signed long long`**, **`signed long long int`**

- **`unsigned long long`**, **`unsigned long long int`**

**Microsoft 固有** の整数型には、特定の幅 **`__int8`** 、 **`__int16`** 型、型、および型が含ま **`__int32`** **`__int64`** れます。 これらの型は、 **`signed`** および修飾子を使用でき **`unsigned`** ます。 **`__int8`** データ型は **`char`** 型と同じ意味であり、 **`__int16`** は **`short`** 型と同じ意味であり、 **`__int32`** は **`int`** 型と同じ意味であり、 **`__int64`** は **`long long`** 型と同じ意味です。

## <a name="sizes-of-built-in-types"></a>組み込み型のサイズ

多くの組み込み型には、実装定義のサイズがあります。 次の表に、Microsoft C++ の組み込み型に必要なストレージの容量を示します。 特に、 **`long`** 64 ビットのオペレーティングシステムでも、は4バイトです。

| Type | サイズ |
|--|--|
| **`bool`**, **`char`**, **`char8_t`**, **`unsigned char`**, **`signed char`**, **`__int8`** | 1 バイト |
| **`char16_t`**, **`__int16`**, **`short`**, **`unsigned short`**, **`wchar_t`**, **`__wchar_t`** | 2 バイト |
| **`char32_t`**, **`float`**, **`__int32`**, **`int`**, **`unsigned int`**, **`long`**, **`unsigned long`** | 4 バイト |
| **`double`**, **`__int64`**, **`long double`**, **`long long`**, **`unsigned long long`** | 8 バイト |

各型の値の範囲の概要については、「 [データ型の範囲](data-type-ranges.md) 」を参照してください。

型変換の詳細については、「 [標準変換](standard-conversions.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ型の範囲](data-type-ranges.md)
