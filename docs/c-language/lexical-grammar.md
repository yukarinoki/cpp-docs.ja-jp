---
title: C 字句文法
description: Microsoft C/C++ コンパイラによって実装されている標準の C 言語字句文法について説明します。
ms.date: 10/30/2020
helpviewer_keywords:
- lexical grammar
ms.assetid: cb5847fa-aef3-47f5-8825-97c2bf4a3d87
ms.openlocfilehash: d0ee2c9e93f3be1a06e264b4c60ec9a89410bb79
ms.sourcegitcommit: 4abc6c4c9694f91685cfd77940987e29a51e3143
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/03/2020
ms.locfileid: "93238500"
---
# <a name="c-lexical-grammar"></a>C 字句文法

## <a name="tokens"></a><a name="tokens"></a> トークン

*`token`* :\
&emsp;*`keyword`*\
&emsp;*`identifier`*\
&emsp;*`constant`*\
&emsp;*`string-literal`*\
&emsp;*`punctuator`*

*`preprocessing-token`* :\
&emsp;*`header-name`*\
&emsp;*`identifier`*\
&emsp;*`pp-number`*\
&emsp;*`character-constant`*\
&emsp;*`string-literal`*\
&emsp;*`punctuator`*\
&emsp;上記のいずれでもない空白以外の各文字

## <a name="keywords"></a><a name="keywords"></a> キーワード

*`keyword`* : 次のいずれか\
&emsp;**`auto`** **`break`** **`case`** **`char`** **`const`** **`continue`**\
&emsp;**`default`** **`do`** **`double`** **`else`** **`enum`** **`extern`**\
&emsp;**`float`** **`for`** **`goto`** **`if`** **`inline`** **`int`** **`long`**\
&emsp;**`register`** **`restrict`** **`return`** **`short`** **`signed`**\
&emsp;**`sizeof`** **`static`** **`struct`** **`switch`** **`typedef`** **`union`**\
&emsp;**`unsigned`** **`void`** **`volatile`** **`while`** **`_Alignas`**\
&emsp;**`_Alignof`** **`_Atomic`** **`_Bool`** **`_Complex`** **`_Generic`**\
&emsp;**`_Imaginary`** **`_Noreturn`** **`_Static_assert`**\
&emsp;**`_Thread_local`**

その他の Microsoft 固有のキーワードの一覧については、「[C キーワード](./c-keywords.md)」を参照してください。

## <a name="identifiers"></a><a name="identifiers"></a> 識別子

*`identifier`* :\
&emsp;*`identifier-nondigit`*\
&emsp;*`identifier`* *`identifier-nondigit`*\
&emsp;*`identifier`* *`digit`*

*`identifier-nondigit`* :\
&emsp;*`nondigit`*\
&emsp;*`universal-character-name`*\
&emsp;実装で定義されている他の文字

*`nondigit`* : 次のいずれか\
&emsp;**`_`** **`a`** **`b`** **`c`** **`d`** **`e`** **`f`** **`g`** **`h`** **`i`** **`j`** **`k`** **`l`** **`m`**\
&emsp;**`n`** **`o`** **`p`** **`q`** **`r`** **`s`** **`t`** **`u`** **`v`** **`w`** **`x`** **`y`** **`z`**\
&emsp;**`A`** **`B`** **`C`** **`D`** **`E`** **`F`** **`G`** **`H`** **`I`** **`J`** **`K`** **`L`** **`M`**\
&emsp;**`N`** **`O`** **`P`** **`Q`** **`R`** **`S`** **`T`** **`U`** **`V`** **`W`** **`X`** **`Y`** **`Z`**

*`digit`* : 次のいずれか\
&emsp;**`0`** **`1`** **`2`** **`3`** **`4`** **`5`** **`6`** **`7`** **`8`** **`9`**

*`universal-character-name`* :\
&emsp;**`\u`** *`hex-quad`*\
&emsp;**`\U`** *`hex-quad`* *`hex-quad`*

*`hex-quad`* :\
&emsp;*`hexadecimal-digit`* *`hexadecimal-digit`* *`hexadecimal-digit`* *`hexadecimal-digit`*

## <a name="constants"></a><a name="constants"></a> 定数

*`constant`* :\
&emsp;*`integer-constant`*\
&emsp;*`floating-constant`*\
&emsp;*`enumeration-constant`*\
&emsp;*`character-constant`*

*`integer-constant`* :\
&emsp; *`decimal-constant`* *`integer-suffix`* <sub>opt</sub>\ 
&emsp; *`binary-constant`* <sup>1</sup> *`integer-suffix`* <sub>opt</sub>\
&emsp; *`octal-constant`* *`integer-suffix`* <sub>opt</sub>\ 
&emsp; *`hexadecimal-constant`* *`integer-suffix`* <sub>opt</sub>

*`decimal-constant`* :\
&emsp;*`nonzero-digit`*\
&emsp;*`decimal-constant`* *`digit`*

*`binary-constant`* :<sup>1</sup>\
&emsp;*`binary-prefix`* *`binary-digit`*\
&emsp;*`binary-constant`* *`binary-digit`*

*`binary-prefix`* <sup>1</sup>: 次のいずれか\
&emsp;**`0b`** **`0B`**

*`binary-digit`* <sup>1</sup>: 次のいずれか\
&emsp;**`0`** **`1`**

*`octal-constant`* :\
&emsp;**`0`**\
&emsp;*`octal-constant`* *`octal-digit`*

*`hexadecimal-constant`* :\
&emsp;*`hexadecimal-prefix`* *`hexadecimal-digit`*\
&emsp;*`hexadecimal-constant`* *`hexadecimal-digit`*

*`hexadecimal-prefix`* : 次のいずれか\
&emsp;**`0x`** **`0X`**

*`nonzero-digit`* : 次のいずれか\
&emsp;**`1`** **`2`** **`3`** **`4`** **`5`** **`6`** **`7`** **`8`** **`9`**

*`octal-digit`* : 次のいずれか\
&emsp;**`0`** **`1`** **`2`** **`3`** **`4`** **`5`** **`6`** **`7`**

*`hexadecimal-digit`* : 次のいずれか\
&emsp;**`0`** **`1`** **`2`** **`3`** **`4`** **`5`** **`6`** **`7`** **`8`**\
&emsp;**`a`** **`b`** **`c`** **`d`** **`e`** **`f`**\
&emsp;**`A`** **`B`** **`C`** **`D`** **`E`** **`F`**

*`integer-suffix`* :\
&emsp; *`unsigned-suffix`* *`long-suffix`* <sub>opt</sub>\ 
&emsp; *`unsigned-suffix`* *`long-long-suffix`* <sub>opt</sub>\ 
&emsp; *`long-suffix`* *`unsigned-suffix`* <sub>opt</sub>\ 
&emsp; *`long-long-suffix`* *`unsigned-suffix`* <sub>opt</sub>

*`unsigned-suffix`* : 次のいずれか\
&emsp;**`u`** **`U`**

*`long-suffix`* : 次のいずれか\
&emsp;**`l`** **`L`**

*`long-long-suffix`* : 次のいずれか\
&emsp;**`ll`** **`LL`**

*`floating-constant`* :\
&emsp;*`decimal-floating-constant`*\
&emsp;*`hexadecimal-floating-constant`*

*`decimal-floating-constant`* :\
&emsp; *`fractional-constant`* *`exponent-part`* <sub>opt</sub> *`floating-suffix`* <sub>opt</sub>\
&emsp; *`digit-sequence`* *`exponent-part`* *`floating-suffix`* <sub>opt</sub>

*`hexadecimal-floating-constant`* :\
&emsp; *`hexadecimal-prefix`* *`hexadecimal-fractional-constant`* *`binary-exponent-part`* <sub>opt</sub> *`floating-suffix`* <sub>opt</sub>\
&emsp; *`hexadecimal-prefix`* *`hexadecimal-digit-sequence`* *`binary-exponent-part`* *`floating-suffix`* <sub>opt</sub>

*`fractional-constant`* :\
&emsp; *`digit-sequence`* <sub>opt</sub> **`.`** *`digit-sequence`* \
&emsp;*`digit-sequence`*  **`.`**

*`exponent-part`* :\
&emsp; **`e`** *`sign`* <sub>opt</sub> *`digit-sequence`*\ 
&emsp; **`E`** *`sign`* <sub>opt</sub> *`digit-sequence`*

*`sign`* : 次のいずれか\
&emsp;**`+`** **`-`**

*`digit-sequence`* :\
&emsp;*`digit`*\
&emsp;*`digit-sequence`* *`digit`*

*`hexadecimal-fractional-constant`* :\
&emsp; *`hexadecimal-digit-sequence`* <sub>opt</sub> **`.`** *`hexadecimal-digit-sequence`* \
&emsp;*`hexadecimal-digit-sequence`*  **`.`**

*`binary-exponent-part`* :\
&emsp; **`p`** *`sign`* <sub>opt</sub> *`digit-sequence`*\ 
&emsp; **`P`** *`sign`* <sub>opt</sub> *`digit-sequence`*

*`hexadecimal-digit-sequence`* :\
&emsp;*`hexadecimal-digit`*\
&emsp;*`hexadecimal-digit-sequence`* *`hexadecimal-digit`*

*`floating-suffix`* : 次のいずれか\
&emsp;**`f`** **`l`** **`F`** **`L`**

*`enumeration-constant`* :\
&emsp;*`identifier`*

*`character-constant`* :\
&emsp;**`'`** *`c-char-sequence`* **`'`**\
&emsp;**`L'`** *`c-char-sequence`* **`'`**

*`c-char-sequence`* :\
&emsp;*`c-char`*\
&emsp;*`c-char-sequence`* *`c-char`*

*`c-char`* :\
&emsp;単一引用符 ( **`'`** )、円記号 ( **`\`** )、または改行文字を除くソース文字セットのメンバー\
&emsp;*`escape-sequence`*

*`escape-sequence`* :\
&emsp;*`simple-escape-sequence`*\
&emsp;*`octal-escape-sequence`*\
&emsp;*`hexadecimal-escape-sequence`*\
&emsp;*`universal-character-name`*

*`simple-escape-sequence`* : 次のいずれか\
&emsp;**`\a`** **`\b`** **`\f`** **`\n`** **`\r`** **`\t`** **`\v`**\
&emsp;**`\'`** **`\"`** **`\\`** **`\?`**

*`octal-escape-sequence`* :\
&emsp;**`\`** *`octal-digit`*\
&emsp;**`\`** *`octal-digit`* *`octal-digit`*\
&emsp;**`\`** *`octal-digit`* *`octal-digit`* *`octal-digit`*

*`hexadecimal-escape-sequence`* :\
&emsp;**`\x`** *`hexadecimal-digit`*\
&emsp;*`hexadecimal-escape-sequence`* *`hexadecimal-digit`*

## <a name="string-literals"></a><a name="string-literals"></a> 文字列リテラル

*`string-literal`* :\
&emsp; *`encoding-prefix`* *`s-char-sequence`* <sub>opt</sub> **`"`**

*`encoding-prefix`* :\
&emsp;**`u8`**\
&emsp;**`u`**\
&emsp;**`U`**\
&emsp;**`L`**

*`s-char-sequence`* :\
&emsp;*`s-char`*\
&emsp;*`s-char-sequence`* *`s-char`*

*`s-char`* :\
&emsp;二重引用符 ( **`"`** )、円記号 ( **`\`** )、改行文字を除くソース文字セットの任意のメンバー\
&emsp;*`escape-sequence`*

## <a name="punctuators"></a><a name="punctuators"></a> 区切り記号

*`punctuator`* : 次のいずれか\
&emsp;**`[`** **`]`** **`(`** **`)`** **`{`** **`}`** **`.`** **`->`**\
&emsp;**`++`** **`--`** **`&`** **`*`** **`+`** **`-`** **`~`** **`!`**\
&emsp;**`/`** **`%`** **`<<`** **`>>`** **`<`** **`>`** **`<=`** **`>=`** **`==`**\
&emsp;**`!=`** **`^`** **`|`** **`&&`** **`||`** **`?`** **`:`** **`;`** **`...`**\
&emsp;**`=`** **`*=`** **`/=`** **`%=`** **`+=`** **`-=`** **`<<=`** **`>>=`**\
&emsp;**`&=`** **`^=`** **`|=`** **`,`** **`#`** **`##`**\
&emsp;**`<:`** **`:>`** **`<%`** **`%>`** **`%:`** **`%:%:`**

## <a name="header-names"></a>ヘッダー名

*`header-name`* :\
&emsp;**`<`** *`h-char-sequence`* **`>`**\
&emsp;**`"`** *`q-char-sequence`* **`"`**

*`h-char-sequence`* :\
&emsp;*`h-char`*\
&emsp;*`h-char-sequence`* *`h-char`*

*`h-char`* :\
&emsp;改行文字と **`>`** を除くソース文字セットの任意のメンバー

*`q-char-sequence`* :\
&emsp;*`q-char`*\
&emsp;*`q-char-sequence`* *`q-char`*

*`q-char`* :\
&emsp;改行文字と **`"`** を除くソース文字セットの任意のメンバー

## <a name="preprocessing-numbers"></a>プリプロセ番号

*`pp-number`* :\
&emsp;*`digit`*\
&emsp;**`.`** *`digit`*\
&emsp;*`pp-number`* *`digit`* \
&emsp;*`pp-number`* *`identifier-nondigit`*\
&emsp;*`pp-number`* **`e`** *`sign`*\
&emsp;*`pp-number`* **`E`** *`sign`*\
&emsp;*`pp-number`* **`p`** *`sign`*\
&emsp;*`pp-number`* **`P`** *`sign`*\
&emsp;*`pp-number`* **`.`**

<sup>1</sup> *`binary-constant`* 、 *`binary-prefix`* 、 *`binary-digit`* は、Microsoft 固有の拡張機能です。

## <a name="see-also"></a>関連項目

[C 言語の構文概要](../c-language/c-language-syntax-summary.md)
