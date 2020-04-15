---
title: strtold、_strtold_l、wcstold、_wcstold_l
ms.date: 4/2/2020
api_name:
- wcstold
- strtold
- _strtold_l
- _wcstold_l
- _o__strtold_l
- _o__wcstold_l
- _o_strtold
- _o_wcstold
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tcstold_l
- _wcstold_l
- _tcstold
- strtold
- _strtold_l
- wcstold
ms.assetid: 928c0c9a-bc49-445b-8822-100eb5954115
ms.openlocfilehash: 9acc98296651f549ceffb1e1deab350a71747ea5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365360"
---
# <a name="strtold-_strtold_l-wcstold-_wcstold_l"></a>strtold、_strtold_l、wcstold、_wcstold_l

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

*ストソース*<br/>
NULL で終わる変換対象の文字列。

*エンドプター*<br/>
スキャンの終了位置を示す文字へのポインター。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strtold**は、浮動小数点数の値を**長倍精度浮動小数点****double**数として返しますが、表現がオーバーフローを引き起こす場合を除き、関数は +/-**HUGE_VALL**を返します。 **HUGE_VALL**の符号は、表すことができない値の符号と一致します。 **strtold 変換**が実行できない場合、またはアンダーフローが発生した場合は 0 を返します。

**wcstold は** **strtold**と類似した値を返します。 どちらの関数でも、オーバーフローまたはアンダーフローが発生し、無効なパラメータ ハンドラが呼び出された場合 **、errno**は**ERANGE**[に設定](../../c-runtime-library/parameter-validation.md)されます。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

各関数は、入力文字列*strSource*を**長倍**に**変換します。** **strtold**関数は、文字列*strSource*の読み取りを、数値の一部として認識できない最初の文字で停止します。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 **strtold**のワイド文字バージョンは**wcstold です**。*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstold**|**strtold**|**strtold**|**wcstold**|
|**_tcstold_l**|**_strtold_l**|**_strtold_l**|**_wcstold_l**|

現在のロケールの**LC_NUMERIC**カテゴリ設定によって *、 strSource*の基数文字の認識が決まります。 詳細については、「[setlocale、_wsetlocale](setlocale-wsetlocale.md)」を参照してください。 **_l**サフィックスを持たない関数は、現在のロケールを使用します。**_strtold_l**と **_wcstold_l**は、渡されたロケールを使用する点を除いて **、_strtold**と **_wcstold**と同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*endptr*が**NULL**でない場合は、スキャンを停止した文字へのポインタが*endptr*によって指されている位置に格納されます。 変換が実行できない場合 (有効な数字が見つからなかったか、無効なベースが指定されている場合 *)、strSource*の値は*endptr*が指す場所に格納されます。

**strtold**は*strSource*が次の形式の文字列を指すことを想定しています。

[*空白*][*記号*][*数字*][.*]*[ {**d** &#124; **D &#124;** e **e** &#124; **E**} [*符号*]*数字*]

*空白*は空白文字とタブ文字で構成され、無視されます。*符号*はプラス (**+**) または**-** マイナス ( ) のいずれかです。数字*は*1 桁以上の 10 進数です。 小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。 10 進数の後には指数部を指定できます。指数部は、指数部の開始文字 (**d**、**D**、**e**、**E**) および必要に応じて符号付き整数で構成されます。 指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。 この形式に一致しない文字を見つけるとスキャンを停止します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**ストトルド**, **_strtold_l**|\<stdlib.h>|
|**wcstold**, **_wcstold_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[マルチバイト文字シーケンスの解釈](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol、wcstol、_strtol_l、_wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
[localeconv](localeconv.md)<br/>
[_create_locale、_wcreate_locale](create-locale-wcreate-locale.md)<br/>
[_free_locale](free-locale.md)<br/>
