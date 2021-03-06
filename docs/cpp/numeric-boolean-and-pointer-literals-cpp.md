---
title: 数値、ブール値、およびポインターのリテラル (C++)
description: 整数、浮動小数点、ブール値、およびポインターのリテラルの C++ 標準言語形式。
ms.date: 11/04/2016
helpviewer_keywords:
- literals, C++
- constants, literals
- literals [C++]
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
ms.openlocfilehash: f817fcca35a741dac29047e214897758cdc93edb
ms.sourcegitcommit: c0c9cdae79f19655e809a4979227c51bb19cff63
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/05/2021
ms.locfileid: "102236713"
---
# <a name="numeric-boolean-and-pointer-literals"></a>数値、ブール値、およびポインターのリテラル

リテラルとは、値を直接に表すプログラム要素です。 この記事では、整数型、浮動小数点型、ブール型、およびポインター型のリテラルについて説明します。 文字列リテラルと文字リテラルの詳細については、「 [文字列リテラルと文字リテラル (C++)](../cpp/string-and-character-literals-cpp.md)」を参照してください。 また、これらのカテゴリのいずれかに基づいて独自のリテラルを定義することもできます。 詳細については、「 [ユーザー定義リテラル (C++)](../cpp/user-defined-literals-cpp.md)」を参照してください。

リテラルは多様なコンテキストで使用できますが、最も一般的な用途は、名前付きの変数を初期化することと、関数に引数を渡すことです。

```cpp
const int answer = 42;      // integer literal
double d = sin(108.87);     // floating point literal passed to sin function
bool b = true;              // boolean literal
MyClass* mc = nullptr;      // pointer literal
```

リテラルの解釈方法やリテラルに与える特定の型を、コンパイラに指示することが重要な場合があります。 これは、リテラルにプレフィックスまたはサフィックスを追加することによって行われます。 たとえば、プレフィックスは、 `0x` その後の数値を16進数値として解釈するようにコンパイラに指示します。たとえば、のように `0x35` なります。 サフィックスは、 `ULL` のように、値を型として扱うようにコンパイラに指示し **`unsigned long long`** `5894345ULL` ます。 各リテラル型のプレフィックスおよびサフィックスの完全な一覧については、次のセクションを参照してください。

## <a name="integer-literals"></a>整数リテラル

整数リテラルは数字で始まり、小数部や指数はありません。 整数リテラルは、10進数、バイナリ、8進数、または16進数形式で指定できます。 必要に応じて、サフィックスを使用して、整数リテラルを符号なしとして指定し、long 型または long long 型として指定することもできます。

プレフィックスまたはサフィックスが存在しない場合、値が適合する場合、コンパイラは整数リテラル値型 **`int`** (32 ビット) を指定します。それ以外の場合は、型 **`long long`** (64 ビット) を指定します。

10 進数の整数リテラルを指定するには、ゼロ以外の数字で指定を始めます。 次に例を示します。

```cpp
int i = 157;        // Decimal literal
int j = 0198;       // Not a decimal number; erroneous octal literal
int k = 0365;       // Leading zero specifies octal literal, not decimal
int m = 36'000'000  // digit separators make large values more readable
```

8 進数の整数リテラルを指定するには、0 で指定を始め、0 ～ 7 の範囲の一連の桁を続けます。 数字の 8 と 9 は、8 進数のリテラルを指定する場合はエラーになります。 次に例を示します。

```cpp
int i = 0377;   // Octal literal
int j = 0397;   // Error: 9 is not an octal digit
```

16進数の整数リテラルを指定するには、またはを使用して仕様を開始し `0x` `0X` ("x" の場合は問題になりません)、からまでの範囲の一連の数字、(または) ~ (または) を指定し `0` `9` `a` `A` `f` `F` ます。 16 進数の `a` (または `A`) ～ `f` (または `F`) は、10 ～ 15 の範囲の値を示します。 次に例を示します。

```cpp
int i = 0x3fff;   // Hexadecimal literal
int j = 0X3FFF;   // Equal to i
```

符号なしの型を指定するには、またはのいずれかのサフィックスを使用し `u` `U` ます。 長い型を指定するには、またはのいずれかのサフィックスを使用し `l` `L` ます。 64 ビットの整数型を指定するには、サフィックスとして LL、ll を使用します。 I64 サフィックスは引き続きサポートされていますが、お勧めしません。 Microsoft に固有のものであり、移植できません。 次に例を示します。

```cpp
unsigned val_1 = 328u;                  // Unsigned value
long val_2 = 0x7FFFFFL;                 // Long value specified
                                        //  as hex literal
unsigned long val_3 = 0776745ul;        // Unsigned long value
auto val_4 = 108LL;                           // signed long long
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long
```

**桁区切り記号**: 単一引用符文字 (アポストロフィ) を使用して、ユーザーが読みやすくなるように、値を大きな数値で区切ることができます。 区切り記号はコンパイルに影響しません。

```cpp
long long i = 24'847'458'121
```

## <a name="floating-point-literals"></a>浮動小数点リテラル

浮動小数点リテラルは、小数部分が必要な値を指定します。 これらの値には小数点 () が含まれ **`.`** 、指数を含めることができます。

浮動小数点リテラルには、数値の値を指定する *有効桁* ( *仮数* と呼ばれることもあります) があります。 数値の大きさを指定する *指数* があります。 また、リテラルの型を指定する省略可能なサフィックスがあります。 有効桁は、数字のシーケンス、ピリオド、および数値の小数部を表す省略可能な一連の数字で構成されます。 次に例を示します。

```cpp
18.46
38.
```

指数部がある場合は、次の例に示すように、10 の累乗として数値の大きさを指定します。

```cpp
18.46e0      // 18.46
18.46e1      // 184.6
```

指数は、またはを使用して指定できます `e` `E` 。同じ意味を持ち、省略可能な符号 (+ または-) と一連の数字が続きます。  指数部がある場合、`18E0` などの整数では後続の小数点は不要です。

浮動小数点リテラルの既定値は型 **`double`** です。 サフィックス、またはまたはまたはを使用して `f` `l` (サフィックスでは `F` `L` 大文字と小文字が区別されません)、リテラルはまたはとして指定でき **`float`** **`long double`** ます。

**`long double`** との **`double`** 表現は同じですが、同じ型ではありません。 たとえば、次のようなオーバーロードされた関数を使用できます。

```cpp
void func( double );
```

and

```cpp
void func( long double );
```

## <a name="boolean-literals"></a>ブール型リテラル

ブール型リテラルは **`true`** と **`false`** です。

## <a name="pointer-literal-c11"></a>ポインター型リテラル (C++11)

C++ では、 [`nullptr`](../cpp/nullptr.md) ゼロ初期化ポインターを指定するためにリテラルが導入されています。 移植可能なコードでは、のように、 **`nullptr`** 整数型のゼロまたはマクロの代わりにを使用する必要があり `NULL` ます。

## <a name="binary-literals-c14"></a>バイナリ リテラル (C++14)

`0B` または `0b` をプレフィックスとして使用することにより、その後に一連の 1 と 0 が続く、バイナリ文字列を指定することができます。

```cpp
auto x = 0B001101 ; // int
auto y = 0b000001 ; // int
```

## <a name="avoid-using-literals-as-magic-constants"></a>"マジック定数" としてリテラルを使用しないでください。

常に適切なプログラミング方法であるとは言えませんが、リテラルは式およびステートメント内で直接使用できます。

```cpp
if (num < 100)
    return "Success";
```

前の例では、"MAXIMUM_ERROR_THRESHOLD" など、明確な意味を示す名前付き定数を使用することをお勧めします。 また、戻り値 "Success" がエンドユーザーに表示される場合は、名前付き文字列定数を使用する方が適切な場合があります。 文字列定数は、他の言語にローカライズできるファイル内の1つの場所に保持できます。 名前付き定数を使用すると、コードの意図を自分や他のユーザーが理解するのに役立ちます。

## <a name="see-also"></a>関連項目

[構文規則](../cpp/lexical-conventions.md)<br/>
[C++ 文字列リテラル](../cpp/string-and-character-literals-cpp.md)<br/>
[C++ ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)
