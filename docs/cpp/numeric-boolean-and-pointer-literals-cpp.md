---
title: 数値、ブール値、およびポインターのリテラル (C++) |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- literals, C++
- constants, literals
- literals [C++]
ms.assetid: 17c09fc3-3ad7-47e2-8b48-ba8ae994edc8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a445e9c435f9e077899a2a473dc5862f98a36bf4
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/01/2018
ms.locfileid: "39405520"
---
# <a name="numeric-boolean-and-pointer-literals--c"></a>数値、ブール値、およびポインターのリテラル (C++)
リテラルとは、値を直接に表すプログラム要素です。 ここでは、整数型、浮動小数点型、ブール値型、およびポインター型のリテラルについて説明します。 文字列と文字リテラルについては、次を参照してください。[文字列と文字リテラル (C++)](../cpp/string-and-character-literals-cpp.md)します。 これらのカテゴリのいずれかに基づく独自のリテラルを定義することもできます。詳細については、次を参照してください[ユーザー定義リテラル (C++)。](../cpp/user-defined-literals-cpp.md)  
  
 . リテラルは多様なコンテキストで使用できますが、最も一般的な用途は、名前付きの変数を初期化することと、関数に引数を渡すことです。  
  
```cpp 
const int answer = 42; // integer literal  
double d = sin(108.87);     //floating point literal passed to sin function  
bool b = true;              // boolean literal  
MyClass* mc = nullptr;      // pointer literal  
```  
  
 リテラルの解釈方法やリテラルに与える特定の型を、コンパイラに指示することが重要な場合があります。 リテラルにプレフィックスまたはサフィックスを追加することによってこれを行います。 たとえば、プレフィックス 0x は、それに続く数値を 16 進数値として解釈するようコンパイラに指示します (0x35 など)。 ULL サフィックスとして、値を処理するようにコンパイラに指示する**unsigned long long 型**5894345ULL のように、型。 各リテラル型のプレフィックスおよびサフィックスの完全な一覧については、次のセクションを参照してください。  
  
## <a name="syntax"></a>構文  
  
## <a name="integer-literals"></a>整数リテラル  
 整数リテラルは数字で始まり、小数部や指数はありません。 整数リテラルには、10 進数、8 進数、または 16 進数形式を指定できます。 符号付きまたは符号なしの型と、long または short の型を指定できます。  
  
 コンパイラは、整数リテラル値の型、プレフィックスまたはサフィックスが存在しない場合、 **int** (32 ビット) の場合、値が収まりそれ以外の場合は付けます型**long** (64 ビット)。  
  
 10 進数の整数リテラルを指定するには、ゼロ以外の数字で指定を始めます。 例えば:  
  
```cpp 
int i = 157;   // Decimal literal  
int j = 0198;       // Not a decimal number; erroneous octal literal  
int k = 0365;       // Leading zero specifies octal literal, not decimal  
int m = 36'000'000  // digit separators make large values more readable  
int   
```  
  
 8 進数の整数リテラルを指定するには、0 で指定を始め、0 ～ 7 の範囲の一連の桁を続けます。 数字の 8 と 9 は、8 進数のリテラルを指定する場合はエラーになります。 例えば:  
  
```cpp 
int i = 0377;   // Octal literal  
int j = 0397;        // Error: 9 is not an octal digit  
```  
  
 16 進数の整数リテラルを指定するには、`0x` または `0X` ("x" の大文字と小文字は区別されません) で指定を始め、`0` ～ `9` と `a` (または `A`) ～ `f` (または `F`) の範囲の一連の桁を続けます。 16 進数の `a` (または `A`) ～ `f` (または `F`) は、10 ～ 15 の範囲の値を示します。 例えば:  
  
```cpp 
int i = 0x3fff;   // Hexadecimal literal  
int j = 0X3FFF;        // Equal to i  
```  
  
 符号なしの型を指定するには、いずれかを使用、`u`または`U`サフィックス。 Long 型を指定するには、いずれかを使用、`l`または`L`サフィックス。 64 ビットの整数型を指定するには、サフィックスとして LL、ll を使用します。 i64 サフィックスはまだサポートされていますが、Microsoft に固有なものであり移植性がないため、使用を避けることをお勧めします。 例えば:  
  
```cpp 
unsigned val_1 = 328u;             // Unsigned value  
long val_2 = 0x7FFFFFL;                 // Long value specified   
                                        //  as hex literal  
unsigned long val_3 = 0776745ul;        // Unsigned long value  
auto val_4 = 108LL;                           // signed long long  
auto val_4 = 0x8000000000000000ULL << 16;     // unsigned long long   
```  
  
 **桁区切り記号**: に多数の人間が読みやすくための場所の値を区切る単一引用符 (アポストロフィ) を使用することができます。 区切り記号はコンパイルに影響しません。  
  
```cpp 
long long i = 24'847'458'121  
```  
  
## <a name="floating-point-literals"></a>浮動小数点リテラル  
 浮動小数点リテラルは、小数部分が必要な値を指定します。 これらの値に小数点が含まれて (**.**) の指数を含めることができます。  
  
 浮動小数点リテラルには、数値の値を指定する "仮数"、数値の大きさを指定する "指数"、およびリテラルの型を指定する省略可能なサフィックスが含まれます。 仮数は、一連の数字の後ろにピリオドを続け、その後ろに数値の小数部分を表す省略可能な一連の数字を続けることで指定されます。 次に例を示します。  
  
```cpp 
18.46  
38.  
```  
  
 指数部がある場合は、次の例に示すように、10 の累乗として数値の大きさを指定します。  
  
```cpp 
18.46e0      // 18.46  
18.46e1           // 184.6  
```  
  
 使用して、指数部を指定することがあります`e`または`E`、オプションの記号の後に、同じ意味である (+ または -) と一連の数字です。  指数部がある場合、`18E0` などの整数では後続の小数点は不要です。  
  
 型に既定の浮動小数点リテラル**二重**します。 サフィックスを使用して`f`または`l`(または`F`または`L`—、サフィックスが、大文字小文字を区別することはありません)、リテラルとして指定できます**float**または**long double**、それぞれします。  
  
 **Long double**と**二重**同じ表現であるが、これらは同じ型。 たとえば、次のようにオーバーロードされた関数を指定できます。  
  
```cpp 
void func( double );  
```  
  
 と、呼び出し  
  
```cpp 
void func( long double );  
```  
  
## <a name="boolean-literals"></a>ブール型リテラル  
 ブール型リテラルは**true**と**false**します。  
  
## <a name="pointer-literal-c11"></a>ポインター型リテラル (C++11)  
 C++ の紹介、 [nullptr](../cpp/nullptr.md)ゼロ初期化ポインターを指定するリテラル。 移植可能なコードで**nullptr**整数型の 0 または NULL などのマクロの代わりに使用する必要があります。  
  
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
  
 前の例では、"MAXIMUM_ERROR_THRESHOLD"など、明確な意味を伝達する名前付き定数を使用する方がよい場合があります。 戻り値の "Success" がエンドユーザーに表示される場合は、ファイルの 1 つの場所に格納でき他の言語にローカライズできる名前付き文字列定数を使用する方がよい場合があります。 名前付き定数を使用すると、他のユーザーにとってもコードの意図が理解しやすくなります。  
  
## <a name="see-also"></a>関連項目  
 [構文規則](../cpp/lexical-conventions.md)   
 [C++ 文字列リテラル](../cpp/string-and-character-literals-cpp.md)   
 [C++ ユーザー定義リテラル](../cpp/user-defined-literals-cpp.md)