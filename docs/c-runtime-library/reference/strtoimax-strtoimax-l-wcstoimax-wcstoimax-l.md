---
title: strtoimax、_strtoimax_l、wcstoimax、_wcstoimax_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- wcstoimax
- _wcstoimax_l
- _strtoimax_l
- strtoimax
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
- wcstoimax
- _tcstoimax
- strtoimax
- _wcstoimax_l
- _strtoimax_l
- _tcstoimax_l
dev_langs:
- C++
helpviewer_keywords:
- strtoimax funciton
- conversion functions
- _strtoimax_l function
- _wcstoimax_l function
- wcstoimax function
ms.assetid: 4530d3dc-aaac-4a76-b7cf-29ae3c98d0ae
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 58ee8f4cbceaa2972de9a40a4192b1175b25488d
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416541"
---
# <a name="strtoimax-strtoimaxl-wcstoimax-wcstoimaxl"></a>strtoimax、_strtoimax_l、wcstoimax、_wcstoimax_l

サポートされる最大の符号付き整数型の整数値に文字列を変換します。

## <a name="syntax"></a>構文

```C
intmax_t strtoimax(
   const char *strSource,
   char **endptr,
   int base
);
intmax_t wcstoimax(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
intmax_t _strtoimax_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
intmax_t _wcstoimax_l(
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

**strtoimax**文字列で表される値を返します*strSource*、形式がオーバーフローを発生する場合を除く、その場合を返します**INTMAX_MAX**または**INTMAX_MIN**、および**errno**に設定されている**ERANGE**です。 この関数は、変換を実行できない場合には 0 を返します。 **wcstoimax**戻り値を返します**strtoimax**です。

**INTMAX_MAX**と**INTMAX_MIN** stdint.h で定義されます。

場合*strSource*は**NULL**または*基本*が 0 でないと、2 未満または 36 を超える**errno**に設定されている**EINVAL**.

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**Strtoimax**関数に変換*strSource*を**intmax_t**です。 ワイド文字バージョン**strtoimax**は**wcstoimax**以外の場合はその*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。 どちらの関数は、文字列の読み取りを停止*strSource*数値の一部として認識できない最初の文字です。 大きいか等しいには、最初の数値文字がある可能性がありますか終端の null 文字あります*基本*です。

ロケールの**LC_NUMERIC**カテゴリの設定によっての小数点文字の認識*strSource*。 詳細については、を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 関数がない、 **_l**サフィックスは現在のロケールを使用します。**_strtoimax_l**と **_wcstoimax_l**が付いていない対応する関数と同じでは、 **_l**サフィックスをロケールを代わりに使用する点を除いての渡されます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*は**NULL**が指す位置に、スキャンを停止させた文字へのポインターが格納されている*endptr*です。 変換を実行できない場合 (有効な数字が見つからないか無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*です。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoimax**|**strtoimax**|**strtoimax**|**wcstoimax**|
|**_tcstoimax_l**|**strtoimax_l**|**_strtoimax_l**|**_wcstoimax_l**|

**strtoimax**が必要ですが*strSource*して次の形式の文字列を指します。

> [*空白*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }] [*桁*&#124; *文字*]  

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*桁*は 1 つ以上の 10 進数字です。*文字*1 つまたは複数の文字は、'a' から 'z' ('A' ~ 'Z')。 この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*2 ~ 36 の間は、数値の基数として使用されます。 場合*基本*0 によって示される文字列の先頭の文字は、 *strSource*基数を判定するために使用します。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*0 は、スキャンされた最初の文字が '0' と見なされます、8 進数と、'8' または '9' の文字は、スキャンは停止します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtoimax**、 **_strtoimax_l**、 **wcstoimax**、 **_wcstoimax_l**|\<inttypes.h>|

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
[strtoumax、_strtoumax_l、wcstoumax、_wcstoumax_l](strtoumax-strtoumax-l-wcstoumax-wcstoumax-l.md)<br/>
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
