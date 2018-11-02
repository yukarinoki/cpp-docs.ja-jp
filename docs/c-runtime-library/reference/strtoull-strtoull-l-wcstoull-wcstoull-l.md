---
title: strtoull、_strtoull_l、wcstoull、_wcstoull_l
ms.date: 11/04/2016
apiname:
- _strtoull_l
- _wcstoull_l
- strtoull
- wcstoull
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
- _wcstoull_l
- _tcstoull
- _tcstoull_l
- wcstoull
- _strtoull_l
- strtoull
helpviewer_keywords:
- strtoull function
- _tcstoull_l function
- _tcstoull function
- _wcstoull_l function
- _strtoull_l function
- wcstoull function
ms.assetid: 36dac1cc-e901-40a0-8802-63562d6d01df
ms.openlocfilehash: f23799b43a356600f48fb0fbf32b4604966c416b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677553"
---
# <a name="strtoull-strtoulll-wcstoull-wcstoulll"></a>strtoull、_strtoull_l、wcstoull、_wcstoull_l

文字列を符号なし長整数の値に変換します。

## <a name="syntax"></a>構文

```C
unsigned long long strtoull(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long long _strtoull_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long long wcstoull(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long long _wcstoull_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる変換対象の文字列。

*endptr*<br/>
スキャンの終了位置を示す文字へのポインター。

*base*<br/>
使用する基数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strtoull**存在する場合は、変換後の値を返しますまたは**ULLONG_MAX**オーバーフローが発生します。 **strtoull**変換を実行できない場合は 0 を返します。 **wcstoull**と同様に値を返します**strtoull**します。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローやアンダー フローが発生した場合。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

入力文字列の各関数に変換します*strSource*を**符号なし****長い****長い**整数値。

**strtoull**文字列の読み取りを停止する*strSource*数値の一部として認識できない最初の文字。 終端の null 文字がありますまたは最初の数値文字に以上である可能性がある*基本*します。 設定、 **LC_NUMERIC**ロケールのカテゴリの小数点文字の認識されます*strSource*; 詳細についてを参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md). **strtoull**と**wcstoull** ; 現在のロケールを使用します **_strtoull_l**と **_wcstoull_l**代わりに渡されるロケールは同一それ以外の場合。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*ない**NULL**、場所を指しているスキャンを停止させた文字へのポインターが格納されている*endptr*します。 変換を実行できない場合 (有効な数字が見つからないか、無効な base を指定した) の値*strSource*によってポイントされている位置に格納されて*endptr*します。

**wcstoull**のワイド文字バージョンは、 **strtoull**とその*strSource*引数はワイド文字の文字列。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoull**|**strtoull**|**strtoull**|**wcstoull**|
|**_tcstoull_l**|**strtoull_l**|**_strtoull_l**|**_wcstoull_l**|

**strtoull**が必要ですが*strSource*次の形式の文字列を指すようにします。

> [*空白*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }] [*桁*&#124; *文字*]  

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。 *数字*は 1 つ以上の 10 進数字。 *文字*1 つまたは複数の文字を 'a' から 'z' (または 'A' ~ 'Z')。 この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*が 2 ~ 36 の間の数値の基数として使用されます。 場合*基本*は 0 が指す文字列の先頭の文字です。 *strSource*を使用して、ベースを決定します。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*は 0 です。 および、スキャンされた最初の文字は '0'、8 進数の整数が想定されますと、'8' または '9' の文字が、スキャンを停止します。 **strtoull**により、プラス記号 (**+**) またはマイナス記号 (**-**) プレフィックスは先頭の負符号は戻り値の符号が反転されることを示します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strtoull**|\<stdlib.h>|
|**wcstoull**|\<stdlib.h> または \<wchar.h>|
|**_strtoull_l**|\<stdlib.h>|
|**_wcstoull_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[strtod](strtod-strtod-l-wcstod-wcstod-l.md) の例をご覧ください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol、wcstol、_strtol_l、_wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[strtoll、_strtoll_l、wcstoll、_wcstoll_l](strtoll-strtoll-l-wcstoll-wcstoll-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
