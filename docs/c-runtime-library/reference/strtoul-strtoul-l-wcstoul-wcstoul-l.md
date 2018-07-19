---
title: strtoul、_strtoul_l、wcstoul、_wcstoul_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
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
- strtoul
- _tcstoul
- wcstoul
dev_langs:
- C++
helpviewer_keywords:
- _wcstoul_l function
- _tcstoul function
- _strtoul_l function
- string conversion, to integers
- wcstoul function
- strtoul function
- wcstoul_l function
- strtoul_l function
- tcstoul function
ms.assetid: 38f2afe8-8178-4e0b-8bbe-d5c6ad66e3ab
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 341d331d7de675588524a20596b7ebcd27358b5a
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416899"
---
# <a name="strtoul-strtoull-wcstoul-wcstoull"></a>strtoul、_strtoul_l、wcstoul、_wcstoul_l

文字列を符号なし長整数の値に変換します。

## <a name="syntax"></a>構文

```C
unsigned long strtoul(
   const char *strSource,
   char **endptr,
   int base
);
unsigned long _strtoul_l(
   const char *strSource,
   char **endptr,
   int base,
   _locale_t locale
);
unsigned long wcstoul(
   const wchar_t *strSource,
   wchar_t **endptr,
   int base
);
unsigned long _wcstoul_l(
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

**strtoul**存在する場合、変換後の値を返しますまたは**ULONG_MAX**オーバーフローが発生します。 **strtoul**変換を実行できない場合は 0 を返します。 **wcstoul**戻り値を返します**strtoul**です。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローまたはアンダー フローが発生した場合。

戻り値の詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 」を参照してください。

## <a name="remarks"></a>コメント

入力文字列に変換しますこれらの関数の各*strSource*を**符号なし****長い**です。

**strtoul**文字列の読み取りを停止する*strSource*は、数値の一部として認識できない最初の文字です。 大きいか等しいには、最初の数値文字がある可能性がありますか終端の null 文字あります*基本*です。 **LC_NUMERIC** 、ロケールのカテゴリの設定を決定の小数点文字の認識*strSource*。 詳細については、を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md)です。 **strtoul**と**wcstoul**は現在のロケールを使用します。**_strtoul_l**と **_wcstoul_l**は、代わりに渡されたロケール パラメーターを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*は**NULL**、スキャンを停止させた文字へのポインターが指す位置に格納されている*endptr*です。 変換を実行できない場合 (有効な数字が見つからないか無効な base を指定した) の値*strSource*が指す位置に格納されて*endptr*です。

**wcstoul**のワイド文字バージョンは、 **strtoul**以外の場合はその*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul**が必要ですが*strSource*して次の形式の文字列を指します。

> [*空白*] [{**+** &#124; **-**}] [**0** [{ **x**&#124; **X** }] [*桁*&#124; *文字*]  

A*空白*は無視されますスペースやタブ文字で構成されます。 *桁*は 1 つ以上の 10 進数字です。 *文字*1 つまたは複数の文字は、'a' から 'z' ('A' ~ 'Z')。 この形式に一致しない文字を見つけるとスキャンを停止します。 場合*基本*2 ~ 36 の間は、数値の基数として使用されます。 場合*基本*0 によって示される文字列の先頭の文字は、 *strSource*基数を判定するために使用します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 たとえば場合、*基本*0 は、スキャンされた最初の文字が '0' と見なされます、8 進数と、'8' または '9' の文字は、スキャンは停止します。 **strtoul** 、プラス記号を許可 (**+**) またはマイナス記号 (**-**) 符号プレフィックス以外の場合はマイナス記号は、戻り値を否定することを示します。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtoul**|\<stdlib.h>|
|**wcstoul**|\<stdlib.h> または \<wchar.h>|
|**_strtoul_l**|\<stdlib.h>|
|**_wcstoul_l**|\<stdlib.h> または \<wchar.h>|

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
[atof、_atof_l、_wtof、_wtof_l](atof-atof-l-wtof-wtof-l.md)<br/>
