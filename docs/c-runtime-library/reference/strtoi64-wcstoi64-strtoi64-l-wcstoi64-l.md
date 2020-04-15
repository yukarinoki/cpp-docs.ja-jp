---
title: _strtoi64、_wcstoi64、_strtoi64_l、_wcstoi64_l
ms.date: 4/2/2020
api_name:
- _strtoi64
- _strtoi64_l
- _wcstoi64_l
- _wcstoi64
- _o__strtoi64
- _o__strtoi64_l
- _o__wcstoi64
- _o__wcstoi64_l
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
- _strtoi64
- strtoi64
- _stroi64_l
- _wcstoi64_l
- wcstoi64_l
- _wcstoi64
- wcstoi64
- strtoi64_l
helpviewer_keywords:
- _strtoi64 function
- _wcstoi64 function
- _strtoi64_l function
- string conversion, to integers
- _wcstoi64_l function
- strtoi64_l function
- wcstoi64 function
- strtoi64 function
- wcstoi64_l function
ms.assetid: ea2abc50-7bfe-420e-a46b-703c3153593a
ms.openlocfilehash: 8dcdff4cf6f3eff191dc126583c1ca8290133e02
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365129"
---
# <a name="_strtoi64-_wcstoi64-_strtoi64_l-_wcstoi64_l"></a>_strtoi64、_wcstoi64、_strtoi64_l、_wcstoi64_l

文字列を **__int64**値に変換します。

## <a name="syntax"></a>構文

```C
__int64 _strtoi64(
   const char *strSource,
   char **endptr,
   int base
);
__int64 _wcstoi64(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
__int64 _strtoi64_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
__int64 _wcstoi64_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*ストソース*<br/>
NULL で終わる変換対象の文字列。

*エンドプター*<br/>
スキャンの終了位置を示す文字へのポインター。

*base*<br/>
使用する基数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**_strtoi64**は文字列*strSource*で表される値を返しますが、その場合は、その表現がオーバーフローを起こす場合を除き **、_I64_MAX**または **_I64_MIN**を返します。 この関数は、変換を実行できない場合には 0 を返します。 **_wcstoi64**は**strtoi64**と同様に値を返します。

**_I64_MAX**と **_I64_MIN**は LIMITS で定義されます。H。

*strSource*が**NULL**であるか、*またはベース*が 0 以外の値で、2 より小さいか 36 より大きい場合 **、errno**は**EINVAL**に設定されます。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_strtoi64**関数は*strSource*を **__int64**に変換します。 どちらの関数も、文字列*strSource*の読み取りを、数値の一部として認識できない最初の文字で停止します。 これは、終端の NULL 文字である場合も、最初の数値文字が*base*以上である場合もあります。 **_wcstoi64**はワイド文字の **_strtoi64**です。*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoi64**|**_strtoi64**|**_strtoi64**|**_wcstoi64**|
|**_tcstoi64_l**|**_strtoi64_l**|**_strtoi64_l**|**_wcstoi64_l**|

ロケールの**LC_NUMERIC**カテゴリ設定によって *、strSource*の基数文字の認識が決まります。詳細については、 [setlocale](setlocale-wsetlocale.md)を参照してください。 サフィックス_lを持たない関数は、現在のロケールを使用します。**_strtoi64_l**と **_wcstoi64_l**は、_l**サフィックスを**持たない対応する関数と同じですが、代わりに渡されたロケールが使用されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*endptr*が**NULL**でない場合は、スキャンを停止した文字へのポインタが*endptr*が指す位置に格納されます。 変換が実行できない場合 (有効な数字が見つからなかったか、無効なベースが指定されている場合 *)、strSource*の値は*endptr*が指す場所に格納されます。

**_strtoi64**は*strSource*が次の形式の文字列を指すことを想定しています。

> [*空白*][{**+** **-**&#124; } ][**0** [ { **x x** &#124; **X** } ] [*&#124;文字の数字*] *letters*

*空白*は空白文字とタブ文字で構成され、無視されます。*数字*は 1 桁以上の 10 進数です。*文字*は、'a' から 'z' (または 'A' から 'Z') までの 1 つ以上の文字です。  この形式に一致しない文字を見つけるとスキャンを停止します。 *base*が 2 から 36 の間の場合、その数のベースとして使用されます。 *base*が 0 の場合は *、strSource*が指す文字列の初期文字を使用してベースを決定します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 例えば *、base*が 0 で、最初にスキャンされた文字が '0' の場合、8 進数が想定され、'8' または '9' 文字がスキャンを停止します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_strtoi64**, **_strtoi64_l**|\<stdlib.h>|
|**_wcstoi64**, **_wcstoi64_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
