---
title: strtol、wcstol、_strtol_l、_wcstol_l
ms.date: 11/04/2016
apiname:
- strtol
- wcstol
- _strtol_l
- _wcstol_l
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
ms.openlocfilehash: 73df5dd3ffcd4a9b2fca8b6b713b645ef94addb5
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326720"
---
# <a name="strtol-wcstol-strtoll-wcstoll"></a>strtol、wcstol、_strtol_l、_wcstol_l

文字列を長整数値に変換します。

## <a name="syntax"></a>構文

```C
long strtol(
   const char *strSource,
   char **endptr,
   int base
);
long wcstol(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long _strtol_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long _wcstol_l(
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

**strtol**文字列で表される値を返します*strSource*オーバーフローを引き起こす、ときに場合を返しますただし、 **LONG_MAX**または**LONG_。MIN**します。 **strtol**変換を実行できない場合は 0 を返します。 **wcstol**と同様に値を返します**strtol**します。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローやアンダー フローが発生した場合。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Strtol**関数に変換します*strSource*を**長い**します。 **strtol**文字列の読み取りを停止する*strSource*数値の一部として認識できない最初の文字。 終端の null 文字がありますまたは以上の値には、最初の数値文字がある可能性があります*基本*します。

**wcstol**のワイド文字バージョンは、 **strtol**、 *strSource*引数はワイド文字の文字列。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstol**|**strtol**|**strtol**|**wcstol**|
|**_tcstol_l**|**_strtol_l**|**_strtol_l**|**_wcstol_l**|

現在のロケールの**LC_NUMERIC**の小数点文字のカテゴリの設定が認識*strSource*; 詳細についてを参照してください[setlocale](setlocale-wsetlocale.md)します。 せず、関数、 **_l**サフィックスを使用して、現在のロケール **_strtol_l**と **_wcstol_l**ことがなく対応する関数と同じですが、 **_l**サフィックスを代わりに渡されたロケールを使用する点を除いて。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*ない**NULL**、スキャンを停止させた文字へのポインターが指す位置に格納されている*endptr*します。 変換を実行できない場合 (有効な数字が見つからないか、無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*します。

**strtol**が必要ですが*strSource*次の形式の文字列を指すようにします。

> [*空白*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }] [*桁*&#124; *文字*]  

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*桁*は 1 つ以上の 10 進数字です。*文字*1 つまたは複数の文字を 'a' から 'z' (または 'A' ~ 'Z')。  この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*が 2 ~ 36 の間の数値の基数として使用されます。 場合*基本*は 0 が指す文字列の先頭の文字です。 *strSource*を使用して、ベースを決定します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*は 0 です。 および、スキャンされた最初の文字は '0'、8 進数の整数が想定されますと、'8' または '9' の文字は、スキャンは停止します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strtol**|\<stdlib.h>|
|**wcstol**|\<stdlib.h> または \<wchar.h>|
|**_strtol_l**|\<stdlib.h>|

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
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
