---
title: strtod、_strtod_l、wcstod、_wcstod_l | Microsoft Docs
ms.custom: ''
ms.date: 10/20/2017
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstod
- _wcstod_l
- _strtod_l
- strtod
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcstod
- strtod
- wcstod
- _strtod_l
- _wcstod_l
- stdlib/strtod
- corecrt_wstdlib/wcstod
- stdlib/_strtod_l
- corecrt_wstdlib/_wcstod_l
dev_langs:
- C++
helpviewer_keywords:
- wcstod_l function
- tcstod_l function
- _tcstod_l function
- strtod function
- _wcstod_l function
- wcstod function
- strtod_l function
- tcstod function
- _tcstod function
- _strtod_l function
- string conversion, to floating point values
ms.assetid: 0444f74a-ba2a-4973-b7f0-1d77ba88c6ed
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9abf6ea87681470f4e1d290a9a0059efb41de499
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417492"
---
# <a name="strtod-strtodl-wcstod-wcstodl"></a>strtod、_strtod_l、wcstod、_wcstod_l

文字列を倍精度値に変換します。

## <a name="syntax"></a>構文

```C
double strtod(
   const char *strSource,
   char **endptr
);
double _strtod_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
double wcstod(
   const wchar_t *strSource,
   wchar_t **endptr
);
double wcstod_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる変換対象の文字列。

*endptr*<br/>
スキャンの終了位置を示す文字へのポインター。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strtod**形式が +/-場合、関数が返されます、オーバーフローを発生する場合を除き、浮動小数点数の値を返します**HUGE_VAL**です。 符号**HUGE_VAL**表現できない値の符号と一致します。 **strtod**変換を実行できないか、アンダー フローが発生した場合は 0 を返します。

**wcstod**戻り値を返します**strtod**です。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローまたはアンダー フローが発生し、で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 戻り値の詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

各関数は、入力文字列を変換*strSource*を**二重**です。 **Strtod**関数に変換*strSource*倍精度値にします。 **strtod**文字列の読み取りを停止する*strSource*は、数値の一部として認識できない最初の文字です。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 **wcstod**のワイド文字バージョンは、 **strtod**以外の場合はその*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

**LC_NUMERIC** 、現在のロケールのカテゴリの設定の決定、ポイントの小数点文字の認識*strSource*です。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。 せず、関数、 **_l**サフィックスは現在のロケールを使用します。**_strtod_l**と同じ **_strtod_l**使用する点を除いて、*ロケール*代わりに渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*は**NULL**、スキャンを停止させた文字へのポインターが指す位置に格納されている*endptr*です。 変換を実行できない場合 (有効な数字が見つからないか無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*です。

**strtod**が必要ですが*strSource*形式は次のいずれかの文字列を指す。

[*空白*] [*記号*] {*桁*[*基数**桁*] &#124; *基数**桁*} [{**e** &#124; **E**} [*記号*]*桁*] [*空白*] [*記号*] {**0 x** &#124; **0 X**} {*hexdigits* [*基数* *hexdigits*] &#124; *基数* *hexdigits*} [{**p** &#124;**P**} [*記号*] *hexdigits*] [*空白*] [*記号*] {**INF** &#124; **無限大**} [*空白*] [*記号*] **NAN** [*シーケンス*]

省略可能な先頭*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*記号*はプラス (+) またはマイナス記号 (-) です。*桁*は 1 つ以上の 10 進数字です。*hexdigits*は 1 つ以上の 16 進数字です。*基数*が基数ポイント文字か、ピリオド (.) 既定の"C"ロケール、またはロケール固有の値、現在のロケールが異なる場合、または*ロケール*; 指定、 *シーケンス*英数字のシーケンスは、またはアンダー スコア。 10 進数と 16 進数の両方の番号フォームで基数ポイント文字の前に数字が表示されない場合は少なくとも 1 つにする必要があります文字の後に基数ポイント。 10 進数のフォームでは、10 進数字が続きます開始文字から成る指数部 (**e**または**E**) および必要に応じて符号付き整数。 16 進数のフォームでは、16 進数字が続きます開始文字から成る指数部 (**p**または**P**) し、必要に応じて符号付き 16 進数を表す整数します2 のべき乗の指数。 いずれかの形式、指数部と小数点ポイント文字のどちらが表示されたら、基数ポイント文字と見なされます、文字列の最後の桁に従う。 両方の大文字と小文字を区別、 **INF**と**NAN**フォーム。 これらの形式のいずれかに一致しない最初の文字は、スキャンを停止します。

これらの関数の UCRT のバージョンは Fortran スタイルの変換をサポートしていません (**d**または**D**) 指数の文字です。 この非標準の拡張機能は、CRT の以前のバージョンでサポートされており、コードの互換性に影響する変更点がある可能性があります。 UCRT のバージョンでは、16 進文字列と以前のバージョンでサポートされていませんでした INF 値と NAN 値のラウンド トリップをサポートします。 コードで重大な変更もができます。 たとえば、文字列"0x1a"をによって解釈が**strtod** UCRT のバージョンで 26.0 としてが、以前のバージョンで 0.0 として。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtod**、 **_strtod_l**|C: &lt;stdlib.h> C++: &lt;cstdlib> または &lt;stdlib.h> |
|**wcstod**、 **_wcstod_l**|C: &lt;stdlib.h > または &lt;wchar.h > C++: &lt;cstdlib >、&lt;stdlib.h > または &lt;wchar.h > |

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strtod.c
// This program uses strtod to convert a
// string to a double-precision value; strtol to
// convert a string to long integer values; and strtoul
// to convert a string to unsigned long-integer values.
//

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char   *string, *stopstring;
   double x;
   long   l;
   int    base;
   unsigned long ul;

   string = "3.1415926This stopped it";
   x = strtod( string, &stopstring );
   printf( "string = %s\n", string );
   printf("   strtod = %f\n", x );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "-10110134932This stopped it";
   l = strtol( string, &stopstring, 10 );
   printf( "string = %s\n", string );
   printf("   strtol = %ld\n", l );
   printf("   Stopped scan at: %s\n\n", stopstring );

   string = "10110134932";
   printf( "string = %s\n", string );

   // Convert string using base 2, 4, and 8:
   for( base = 2; base <= 8; base *= 2 )
   {
      // Convert the string:
      ul = strtoul( string, &stopstring, base );
      printf( "   strtol = %ld (base %d)\n", ul, base );
      printf( "   Stopped scan at: %s\n", stopstring );
   }
}
```

```Output
string = 3.1415926This stopped it
   strtod = 3.141593
   Stopped scan at: This stopped it

string = -10110134932This stopped it
   strtol = -2147483648
   Stopped scan at: This stopped it

string = 10110134932
   strtol = 45 (base 2)
   Stopped scan at: 34932
   strtol = 4423 (base 4)
   Stopped scan at: 4932
   strtol = 2134108 (base 8)
   Stopped scan at: 932
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtol、wcstol、_strtol_l、_wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
