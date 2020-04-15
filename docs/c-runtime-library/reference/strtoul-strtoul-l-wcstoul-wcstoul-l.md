---
title: strtoul、_strtoul_l、wcstoul、_wcstoul_l
ms.date: 4/2/2020
api_name:
- _wcstoul_l
- _strtoul_l
- strtoul
- wcstoul
- _o__strtoul_l
- _o__wcstoul_l
- _o_strtoul
- _o_wcstoul
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- strtoul
- _tcstoul
- wcstoul
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
ms.openlocfilehash: 60ae432fb11c5a29da2c4830c2a85305c6eaa46c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81365626"
---
# <a name="strtoul-_strtoul_l-wcstoul-_wcstoul_l"></a>strtoul、_strtoul_l、wcstoul、_wcstoul_l

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

*ストソース*<br/>
NULL で終わる変換対象の文字列。

*エンドプター*<br/>
スキャンの終了位置を示す文字へのポインター。

*base*<br/>
使用する基数。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strtoul は**変換された値 (存在する場合) を返すか、オーバーフロー時**にULONG_MAX**を返します。 **strtoul は**、変換を実行できない場合は 0 を返します。 **wcstoul は** **strtoul**に類似した値を返します。 どちらの関数でも、オーバーフローまたはアンダーフローが発生した場合 **、errno**は**ERANGE**に設定されます。

このコード、およびその他の戻りコードの詳細については[、_doserrno、errno、_sys_errlist、および_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。

## <a name="remarks"></a>解説

これらの関数は、入力文字列*strSource*を**符号なし****長**に変換します。

**strtoul は**、文字列*strSource*の読み取りを、数値の一部として認識できない最初の文字で停止します。 これは、終端の NULL 文字である場合も、最初の数値文字が*base*以上である場合もあります。 ロケールの**LC_NUMERIC**カテゴリ設定によって *、strSource*の基数文字の認識が決まります。詳細については、 [setlocale](setlocale-wsetlocale.md)を参照してください。 **strtoul**と**wcstoul は**現在のロケールを使用します。**_strtoul_l**と **_wcstoul_l**は、渡されたロケールを代わりに使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

*endptr*が**NULL**でない場合は、スキャンを停止した文字へのポインタが*endptr*が指す位置に格納されます。 変換が実行できない場合 (有効な数字が見つからなかったか、無効なベースが指定されている場合 *)、strSource*の値は*endptr*が指す場所に格納されます。

**wcstoul**は **、strtoul**のワイド文字バージョンです。*strSource*引数はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstoul**|**strtoul**|**strtoul**|**wcstoul**|
|**_tcstoul_l**|**strtoul_l**|**_strtoul_l**|**_wcstoul_l**|

**strtoul**は*strSource*が次の形式の文字列を指すことを想定しています。

> [*空白*][{**+** **-**&#124; } ][**0** [ { **x x** &#124; **X** } ] [*&#124;文字の数字*] *letters*

*空白*は、空白文字とタブ文字で構成され、無視されます。 *数字*は 1 桁以上の 10 進数です。 *文字*は、'a' から 'z' (または 'A' から 'Z') までの 1 つ以上の文字です。 この形式に一致しない文字を見つけるとスキャンを停止します。 *base*が 2 から 36 の間の場合、その数のベースとして使用されます。 *base*が 0 の場合は *、strSource*が指す文字列の初期文字を使用してベースを決定します。 最初の文字が 0 で、2 番目の文字が 'x' または 'X' 以外の場合、文字列は 8 進数と解釈されます。 最初の文字が '0' で、2 番目の文字が 'x' または 'X' である場合、文字列は 16 進数と解釈されます。 最初の文字が '1' ～ '9' の間の数値の場合、文字列は 10 進数と解釈されます。 'a' ～ 'z' (または 'A' ～ 'Z') の文字には、10 ～ 35 の値が割り当てられています。*基数*よりも小さい値が割り当てられている文字のみ許可されます。 基数の範囲外にある文字を最初に見つけた時点で、スキャンは停止されます。 例えば *、base*が 0 で、最初にスキャンされた文字が '0' の場合、8 進数が想定され、'8' または '9' 文字がスキャンを停止します。 **strtoul**は、正**+** 符号 (**-**) またはマイナス ( ) 符号のプレフィックスを許可します。先頭の負符号は、戻り値が否定されていることを示します。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**strtoul**|\<stdlib.h>|
|**wcstoul**|\<stdlib.h> または \<wchar.h>|
|**_strtoul_l**|\<stdlib.h>|
|**_wcstoul_l**|\<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
