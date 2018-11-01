---
title: strtof、_strtof_l、wcstof、_wcstof_l
ms.date: 04/05/2018
apiname:
- _strtof_l
- wcstof
- strtof
- _wcstof_l
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
- _tcstof
- _tcstof_l
- stdlib/strtof
- strtof
- stdlib/_strtof_l
- _strtof_l
- corecrt_wstdlib/wcstof
- wcstof
- corecrt_wstdlib/_wcstof_l
- _wcstof_l
helpviewer_keywords:
- _strtof_l function
- _tcstof function
- _wcstof_l function
- wcstof function
- _tcstof_l function
- strtof function
ms.assetid: 52221b46-876d-4fcc-afb1-97512c17a43b
ms.openlocfilehash: 10a50a175685f3e8f7f1241683c7705fd9a9b142
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607923"
---
# <a name="strtof-strtofl-wcstof-wcstofl"></a>strtof、_strtof_l、wcstof、_wcstof_l

文字列を単精度浮動小数点値に変換します。

## <a name="syntax"></a>構文

```C
float strtof(
   const char *strSource,
   char **endptr
);
float _strtof_l(
   const char *strSource,
   char **endptr,
   _locale_t locale
);
float wcstof(
   const wchar_t *strSource,
   wchar_t **endptr
);
float wcstof_l(
   const wchar_t *strSource,
   wchar_t **endptr,
   _locale_t locale
);
```

## <a name="parameters"></a>パラメーター

*strSource*<br/>
NULL で終わる変換対象の文字列。

*endptr*<br/>
スキャンの終了位置を示す文字へのポインター。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**strtof**表現が +/-が返す場合、関数に、オーバーフローを発生する場合を除き、浮動小数点数の値を返します**HUGE_VALF**します。 符号**HUGE_VALF**表現できない値の符号と一致します。 **strtof**変換を実行できないか、アンダー フローが発生した場合は 0 を返します。

**wcstof**と同様に値を返します**strtof**します。 両方の関数に対して**errno**に設定されている**ERANGE**オーバーフローまたはアンダー フローが発生し、」の説明に従って、無効なパラメーター ハンドラーが呼び出された場合[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

各関数は、入力文字列を変換*strSource*を**float**します。 **Strtof**関数に変換します*strSource*単精度値にします。 **strtof**文字列の読み取りを停止する*strSource*数値の一部として認識できない最初の文字。 数値として認識できない最初の文字が、終端の NULL 文字の場合もあります。 **wcstof**のワイド文字バージョンは、 **strtof**、 *strSource*引数はワイド文字の文字列。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcstof**|**strtof**|**strtof**|**wcstof**|
|**_tcstof_l**|**_strtof_l**|**_strtof_l**|**_wcstof_l**|

**LC_NUMERIC** 、現在のロケールのカテゴリの設定は、基数文字が認識を決定します*strSource*; 詳細については、を参照してください[setlocale、_wsetlocale](setlocale-wsetlocale.md). 関数がない、 **_l**サフィックスを使用して、現在のロケールは、サフィックスが付いているものは、代わりに渡されるロケールを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

場合*endptr*ない**NULL**、場所を指しているスキャンを停止させた文字へのポインターが格納されている*endptr*します。 変換を実行できない場合 (有効な数字が見つからないか、無効な base を指定した) の値*strSource*によってポイントされている位置に格納されて*endptr*します。

**strtof**が必要ですが*strSource*次の形式の文字列を指すようにします。

[*空白*] [*サインオン*] [*桁*] [__.__*桁*] [{**e** &#124; **E**} [*サインオン*]*桁*]

A*空白*は無視されますスペースやタブ文字で構成されている可能性があります。*サインオン*が plus (**+**) または負符号 (**-**); と*桁*は 1 つ以上の 10 進数字。 小数点文字の前に数字がない場合は、少なくとも 1 つの数字が小数点文字の後に必要です。 10 進数字の後に、指数部の開始文字で構成される (**e**または**E**) および必要に応じて符号付き整数。 指数部と小数点文字のいずれも指定されない場合は、文字列の最後の数字の後に小数点文字が続くと想定されます。 この形式に一致しない文字を見つけるとスキャンを停止します。

これらの関数の UCRT バージョンは Fortran スタイルの変換をサポートしていません (**d**または**D**) 指数の文字。 この非標準の拡張機能は、CRT の以前のバージョンでサポートされており、コードの互換性に影響する変更点がある可能性があります。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**strtof**、 **_strtof_l**|C: \<stdlib.h> C++: &lt;cstdlib> または \<stdlib.h>|
|**wcstof**、 **_wcstof_l**|C: \<stdlib.h > または \<wchar.h > C++: &lt;cstdlib >、\<stdlib.h > または \<wchar.h >|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_strtof.c
// This program uses strtof to convert a
// string to a single-precision value.

#include <stdlib.h>
#include <stdio.h>

int main( void )
{
   char *string;
   char *stopstring;
   float x;

   string = "3.14159This stopped it";
   x = strtof(string, &stopstring);
   printf("string = %s\n", string);
   printf("   strtof = %f\n", x);
   printf("   Stopped scan at: %s\n\n", stopstring);
}
```

```Output
string = 3.14159This stopped it
   strtof = 3.141590
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
