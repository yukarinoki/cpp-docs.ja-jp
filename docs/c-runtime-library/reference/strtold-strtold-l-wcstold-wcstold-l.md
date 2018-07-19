---
title: strtold、_strtold_l、wcstold、_wcstold_l | Microsoft Docs
ms.custom: ''
ms.date: 04/05/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
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
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
dev_langs:
- C++
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1a5018f9245da77fbadb301a8fa45d1f0f7b4117
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32417078"
---
# <a name="strtold-strtoldl-wcstold-wcstoldl"></a>strtold、_strtold_l、wcstold、_wcstold_l

文字列を long double 精度浮動小数点値に変換します。

## <a name="syntax"></a>構文

```C
long double strtold(
   const char *strSource,
   char **endptr
);
long double _strtold_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
long double wcstold(
   const wchar_t *strSource,
   wchar_t **endptr
);
long double wcstold_l(
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

**strtold**と浮動小数点数の値を返します、**長い****二重**、ときに、引き起こすを除き、オーバーフロー —+/-関数が返す場合は、**返す。** です。 符号**返す。** 表現できない値の符号と一致します。 **strtold**変換を実行できないか、アンダー フローが発生した場合は 0 を返します。

**wcstold**戻り値を返します**strtold**です。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローまたはアンダー フローが発生し、で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

各関数は、入力文字列を変換*strSource*を**長い****二重**です。 **Strtold**関数は、文字列の読み取りを停止する*strSource*は、数値の一部として認識できない最初の文字です。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 ワイド文字バージョン**strtold**は**wcstold**以外の場合はその*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

**LC_NUMERIC** 、現在のロケールのカテゴリの設定を決定の小数点文字の認識*strSource*です。 詳細については、「[setlocale、_wsetlocale](setlocale-wsetlocale.md)」を参照してください。 せず、関数、 **_l**サフィックスは現在のロケールを使用します。**_strtold_l**と **_wcstold_l**と同じ **_strtold**と **_wcstold**ロケールを代わりに使用する点を除いての渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*は**NULL**が指す位置に、スキャンを停止させた文字へのポインターが格納されている*endptr*です。 変換を実行できない場合 (有効な数字が見つからないか無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*です。

**strtold**が必要ですが*strSource*して次の形式の文字列を指します。

[*空白*] [*記号*] [*桁*] [.*桁*] [{**d** &#124; **D** &#124; **e** &#124; **E**} [*記号*]*桁*]

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*記号*か plus (**+**) またはマイナス記号 (**-**); と*桁の数字*は 1 つ以上の 10 進数字。 小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。 10 進数の後には指数部を指定できます。指数部は、指数部の開始文字 (**d**、**D**、**e**、**E**) および必要に応じて符号付き整数で構成されます。 指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。 この形式に一致しない文字を見つけるとスキャンを停止します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtold**、 **_strtold_l**|\<stdlib.h>|
|**wcstold**、 **_wcstold_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strtold.c
// Build with: cl /W4 /Tc crt_strtold.c
// This program uses strtold to convert a
// string to a long double-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   long double x;

   string = "3.1415926535898This stopped it";
   x = strtold(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtold = %.13Lf\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.1415926535898This stopped it
   strtold = 3.1415926535898
   Stopped scan at: This stopped it

```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[マルチバイト文字のシーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol、wcstol、_strtol_l、_wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
