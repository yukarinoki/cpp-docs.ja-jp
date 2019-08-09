---
title: strtod、_strtod_l、wcstod、_wcstod_l
ms.date: 10/20/2017
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
ms.openlocfilehash: c8c2b3b491e2e7265829fa88580529dc757ace8c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376472"
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

**strtod**表現が +/-が返す場合、関数に、オーバーフローを発生する場合を除き、浮動小数点数の値を返します**HUGE_VAL**します。 符号**HUGE_VAL**表現できない値の符号と一致します。 **strtod**変換を実行できないか、アンダー フローが発生した場合は 0 を返します。

**wcstod**と同様に値を返します**strtod**します。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローまたはアンダー フローが発生し、」の説明に従って、無効なパラメーター ハンドラーが呼び出された場合[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 戻り値の詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

各関数は、入力文字列を変換*strSource*を**二重**します。 **Strtod**関数に変換します*strSource*倍精度値にします。 **strtod**文字列の読み取りを停止する*strSource*数値の一部として認識できない最初の文字。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 **wcstod**のワイド文字バージョンは、 **strtod**、 *strSource*引数はワイド文字の文字列。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstod**|**strtod**|**strtod**|**wcstod**|
|**_tcstod_l**|**_strtod_l**|**_strtod_l**|**_wcstod_l**|

**LC_NUMERIC** 、現在のロケールのカテゴリの設定は、基数ポイント文字が認識を決定します。 *strSource*します。 詳細については、「[setlocale](setlocale-wsetlocale.md)」をご覧ください。 せず、関数、 **_l**サフィックスを使用して、現在のロケール **_strtod_l**ヲェヒェケェ ・ **_strtod_l**使用することを除き、*ロケール*代わりに渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*ない**NULL**、スキャンを停止させた文字へのポインターが指す位置に格納されている*endptr*します。 変換を実行できない場合 (有効な数字が見つからないか、無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*します。

**strtod**は*strSource*形式は次のいずれかの文字列を指すようにします。

[*空白*] [*サインオン*] {*桁*[*基数* *桁*] &#124; *基数* *桁*} [{**e** &#124; **E**} [*サインオン*]*桁*] [*空白*] [*サインオン*] {**0 x** &#124; **0 X**} {*hexdigits* [*基数* *hexdigits*] &#124; *基数* *hexdigits*} [{**p** &#124;**P**} [*サインオン*] *hexdigits*] [*空白*] [*サインオン*] {**INF** &#124; **無限大**} [*空白*] [*サインオン*] **NAN** [*シーケンス*]

省略可能なリード*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*サインオン*はプラス (+) またはマイナス記号 (-)。*桁*は 1 つ以上の 10 進数字です。*hexdigits*は 1 つ以上の 16 進数字。*基数*は小数点ポイントの文字のピリオド (.)、既定の"C"ロケールで、またはロケール固有値の現在のロケールが異なる場合、または*ロケール*; 指定、 *シーケンス*英数字のシーケンスまたはアンダー スコア。 10 進数と 16 進数の両方の番号形式で基数ポイントの文字の前に数字が表示されない場合は少なくとも 1 つが後に必要基数ポイントの文字。 10 進数のフォームでは、10 進数字が続きますは指数部の開始文字で構成されています (**e**または**E**) および必要に応じて符号付き整数。 16 進数の形式で、指数部の開始文字で構成される 16 進数の数字を続けてことができます (**p**または**P**) と、必要に応じて符号付き 16 進整数を表す、2 のべき乗の指数。 いずれかの形式では、指数部と小数点ポイントの文字のどちらが表示されたら、基数ポイントの文字と見なされます、文字列の最後の桁に従ってください。 両方で大文字と小文字が、 **INF**と**NAN**フォーム。 これらの形式のいずれかに適合しない最初の文字は、スキャンを停止します。

これらの関数の UCRT バージョンは Fortran スタイルの変換をサポートしていません (**d**または**D**) 指数の文字。 この非標準の拡張機能は、CRT の以前のバージョンでサポートされており、コードの互換性に影響する変更点がある可能性があります。 UCRT バージョンは、16 進文字列と以前のバージョンでサポートされていませんでした INF 値と NAN 値のラウンド トリップをサポートします。 コードで重大な変更もができます。 たとえば、文字列"0x1a"は、によって解釈されるは**strtod** 0.0 以前のバージョンでは、UCRT バージョン 26.0 として。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
