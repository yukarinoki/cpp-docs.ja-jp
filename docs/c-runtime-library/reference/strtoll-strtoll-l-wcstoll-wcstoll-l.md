---
title: strtoll、_strtoll_l、wcstoll、_wcstoll_l
ms.date: 11/04/2016
apiname:
- strtoll
- wcstoll
- _strtoll_l
- _wcstoll_l
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
- _strtoll_l
- _tcstoll_l
- _tcstoll
- _wcstoll_l
- strtoll
- wcstoll
helpviewer_keywords:
- _tcstoll_l function
- _wcstoll_l function
- strtoll function
- wcstoll function
- _tcstoll function
- _strtoll_l function
ms.assetid: e2d05dcf-d3b2-4291-9e60-dee77e540fd7
ms.openlocfilehash: 53ae4ab1d482478c50aa257acdc974569bfc05f7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62269151"
---
# <a name="strtoll-strtolll-wcstoll-wcstolll"></a>strtoll、_strtoll_l、wcstoll、_wcstoll_l

文字列に変換を**長い** **長い**値。

## <a name="syntax"></a>構文

```C
long long strtoll(
   const char *strSource,
   char **endptr,
   int base
);
long long wcstoll(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
long long _strtoll_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
long long _wcstoll_l(
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

**strtoll**文字列で表される値を返します*strSource*、を除き、表現はオーバーフローが発生すると、その場合を返します**LLONG_MAX**または**LLONG_MIN**します。 この関数は、変換を実行できない場合には 0 を返します。 **wcstoll**と同様に値を返します**strtoll**します。

**LLONG_MAX**と**LLONG_MIN**制限で定義されます。H.

場合*strSource*は**NULL**または*基本*0 以外の場合は、いずれか 2 未満または 36 を超えると**errno**に設定されている**EINVAL**.

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Strtoll**関数に変換します*strSource*を**長い** **長い**します。 どちらの関数は、文字列の読み取りを停止*strSource*数値の一部として認識できない最初の文字。 終端の null 文字がありますまたは最初の数値文字に以上である可能性がある*基本*します。 **wcstoll**のワイド文字バージョンは、 **strtoll**、 *strSource*引数はワイド文字の文字列。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoll**|**strtoll**|**strtoll**|**wcstoll**|
|**_tcstoll_l**|**_strtoll_l**|**_strtoll_l**|**_wcstoll_l**|

ロケールの**LC_NUMERIC**の小数点文字のカテゴリの設定が認識*strSource*; 詳細についてを参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)します。 関数がない、 **_l**サフィックスを使用して、現在のロケール **_strtoll_l**と **_wcstoll_l**で渡されるロケールを代わりに使用する点を除いて、サフィックスがない、対応する関数と同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*ない**NULL**、場所を指しているスキャンを停止させた文字へのポインターが格納されている*endptr*します。 変換を実行できない場合 (有効な数字が見つからないか、無効な base を指定した) の値*strSource*によってポイントされている位置に格納されて*endptr*します。

**strtoll**が必要ですが*strSource*次の形式の文字列を指すようにします。

> [*whitespace*] [{ **+** &#124; **-** }] [**0** [{ **x** &#124; **X** }]] [*digits*  &#124; *letters*]

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*桁*は 1 つ以上の 10 進数字です。*文字*1 つまたは複数の文字を 'a' から 'z' (または 'A' ~ 'Z')。 この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*が 2 ~ 36 の間の数値の基数として使用されます。 場合*基本*は 0 が指す文字列の先頭の文字です。 *strSource*を使用して、ベースを決定します。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*は 0 です。 および、スキャンされた最初の文字は '0'、8 進数の整数が想定されますと、'8' または '9' の文字が、スキャンを停止します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strtoll**、 **_strtoll_l**|\<stdlib.h>|
|**wcstoll**、 **_wcstoll_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[localeconv](localeconv.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[文字列を数値に変換する関数](../../c-runtime-library/string-to-numeric-value-functions.md)<br/>
[strtod、_strtod_l、wcstod、_wcstod_l](strtod-strtod-l-wcstod-wcstod-l.md)<br/>
[strtol、wcstol、_strtol_l、_wcstol_l](strtol-wcstol-strtol-l-wcstol-l.md)<br/>
[strtoul、_strtoul_l、wcstoul、_wcstoul_l](strtoul-strtoul-l-wcstoul-wcstoul-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
