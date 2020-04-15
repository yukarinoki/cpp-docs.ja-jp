---
title: strtol, wcstol, _strtol_l, _wcstol_l
ms.date: 4/2/2020
api_name:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- _o__strtol_l
- _o__wcstol_l
- _o_strtol
- _o_wcstol
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
- _wcstol_l
- strtol
- _tcstol
- wcstol
- _strtol_l
- _tcstol_l
helpviewer_keywords:
- wcstol function
- wcstol_l function
- _tcstol function
- string conversion, to integers
- tcstol function
- strtol_l function
- _wcstol_l function
- _strtol_l function
- strtol function
ms.assetid: 1787c96a-f283-4a83-9325-33cfc1c7e240
no-loc:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
- LONG_MAX
- LONG_MIN
- errno
- ERANGE
- EINVAL
- LC_NUMERIC
- _tcstol
- _tcstol_l
- localeconv
- setlocale
- _wsetlocale
- strtod
- _strtod_l
- wcstod
- _wcstod_l
- strtoll
- _strtoll_l
- wcstoll
- _wcstoll_l
- strtoul
- _strtoul_l
- wcstoul
- _wcstoul_l
- atof
- _atof_l
- _wtof
- _wtof_l
ms.openlocfilehash: dbeaf04d34aa20e15de48e99082ed07edb6129ab
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320478"
---
# <a name="strtol-wcstol-_strtol_l-_wcstol_l"></a>strtol、wcstol、_strtol_l、_wcstol_l

文字列を**長整数**に変換します。

## <a name="syntax"></a>構文

```C
long strtol(
   const char *string,
   char **end_ptr,
   int base
);
long wcstol(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base
);
long _strtol_l(
   const char *string,
   char **end_ptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
   const wchar_t *string,
   wchar_t **end_ptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*文字列*\
NULL で終わる変換対象の文字列。

*end_ptr*\
最後に解釈された文字の後の文字を指す出力パラメーター。 **NULL**の場合は無視されます。

*ベース*\
使用する基数。

*ロケール*\
使用するロケール。

## <a name="return-value"></a>戻り値

**strtol**、 **wcstol** **、_strtol_l、****および _wcstol_l**は *、 string*で表される値を返します。 変換できない場合は 0 を返します。 表現がオーバーフローを引き起こすと、LONG_MAXまたは**LONG_MIN**が返されます。 **LONG_MAX**

オーバーフローまたはアンダーフローが発生した場合 **、errno**は**ERANGE**に設定されます。 *文字列*が**NULL**の場合は **、EINVAL**に設定されます。 または、*底が*0 以外で 2 より小さいか、36 より大きい場合。 **ERANGE**、 **EINVAL**、およびその他の戻りコードの詳細については[、_doserrno、エラー、_sys_errlist、および_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。

## <a name="remarks"></a>解説

**strtol**、 **wcstol**、 **_strtol_l**、**および _wcstol_l**関数は*文字列*を**long**に変換します。 数値の一部として認識されない最初の文字で*文字列*の読み取りを停止します。 終端の NULL 文字、または*base*以上の最初の英数字を指定できます。

**wcstol**と **_wcstol_l**は **、strtol**および **_strtol_l**のワイド文字バージョンです。 *文字列*引数はワイド文字列です。 これらの関数は**strtol**と同じように動作し、それ以外**の場合は_strtol_l。** ロケールの**LC_NUMERIC**カテゴリ設定は *、文字列*での基数文字 (小数マーカーまたは小数点) の認識を決定します。 **strtol**関数と**wcstol**関数は、現在のロケールを使用します。 **_strtol_l**し、代わりに渡されたロケールを使用 **_wcstol_l。** 詳細については、「[setlocale]」および[「ロケール](../../c-runtime-library/locale.md)」を参照してください。

*end_ptr*が**NULL**の場合は無視されます。 それ以外の場合は、スキャンを停止した文字へのポインタが *、 end_ptr*が指す位置に格納されます。 有効な数字が見つからない場合、または無効な基数が指定されている場合は、変換できません。 *文字列*の値は *、end_ptr*が指す場所に格納されます。

**strtol**は *、文字列*が次の形式の文字列を指すことを想定しています。

> [*空白*][{**+** **-**&#124; } ][**0** [ **{** x &#124; **X** } ] ] [*英数字*]

角括弧`[ ]`( ) はオプションの要素を囲みます。 中かっこと垂直バー (`{ | }`) は、単一の要素の代替を囲みます。 *空白*は、空白文字とタブ文字で構成され、無視されます。 *英数字*は、10 進数または文字 'a' から 'z' (または 'A から 'Z') です。 このフォームに合わない最初の文字は、スキャンを停止します。 *base*が 2 から 36 の間の場合、その数値のベースとして使用されます。 *base*が 0 の場合、*文字列*が指す文字列の最初の文字がベースを決定するために使用されます。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' でない場合、文字列は 8 進数として解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 文字 'a' から 'z' (または 'A' から 'Z') には、10 から 35 までの値が割り当てられます。 スキャンでは、値が*base*より小さい文字のみを使用できます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば、*文字列*が "01" で始まるとします。 *base*が 0 の場合、スキャナーは 8 進数と見なします。 '8' または '9' 文字はスキャンを停止します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> または \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|
|**_wcstol_l**|\<stdlib.h> または \<wchar.h>|

および**_strtol_l****_wcstol_l** 関数は、標準 C ライブラリの一部ではなく、マイクロソフト固有のものです。 互換性の詳細については、「[互換性](../compatibility.md)」を参照してください。

## <a name="example"></a>例

の例を[strtod](strtod-strtod-l-wcstod-wcstod-l.md)参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../data-conversion.md)\
[ロケール](../locale.md)\
[localeconv](localeconv.md)\
[setlocale, _wsetlocale](setlocale-wsetlocale.md)\
[文字列から数値への関数](../string-to-numeric-value-functions.md)\
[strtod, _strtod_l, wcstod, _wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)\
[strtoll, _strtoll_l, wcstoll, _wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)\
[strtoul, _strtoul_l, wcstoul, _wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)\
[atof, _atof_l, _wtof, _wtof_l](atof-atof-l-wtof-wtof-l.md)
