---
title: atol、_atol_l、_wtol、_wtol_l
ms.date: 4/2/2020
api_name:
- atol
- _wtol_l
- _wtol
- _atol_l
- _o__atol_l
- _o__wtol
- _o__wtol_l
- _o_atol
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
- _atol_l
- _ttol_l
- _tstol_l
- _tstol
- _wtol
- _ttol
- _wtol_l
helpviewer_keywords:
- tstol function
- atol function
- ttol function
- _atol_l function
- _tstol_l function
- string conversion, to integers
- _tstol function
- _ttol function
- _ttol_l function
- atol_l function
- wtol_l function
- _wtol_l function
- wtol function
- _wtol function
ms.assetid: cedfc21c-2d64-4e9c-bd04-bdf60b12db46
ms.openlocfilehash: 30f8375814259cac8c3d7216c636b69acbc7e90a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348756"
---
# <a name="atol-_atol_l-_wtol-_wtol_l"></a>atol、_atol_l、_wtol、_wtol_l

文字列を長整数に変換します。

## <a name="syntax"></a>構文

```C
long atol(
   const char *str
);
long _atol_l(
   const char *str,
   _locale_t locale
);
long _wtol(
   const wchar_t *str
);
long _wtol_l(
   const wchar_t *str,
   _locale_t locale
);
```

### <a name="parameters"></a>パラメーター

*Str*<br/>
変換対象の文字列。

*ロケール*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

各関数は、入力文字を数値として解釈することによって生成された**long**値を返します。 入力をその型の値に変換できない場合 **、atol**の戻り値は 0L です。

大きな正の整数値を持つオーバーフローの場合 **、atol**は**LONG_MAX**返します。大きな負の整数値でオーバーフローした場合 **、LONG_MIN**返されます。 範囲外の場合は **、errno**が**ERANGE**に設定されます。 渡されたパラメーターが**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、0 を返します。

## <a name="remarks"></a>解説

これらの関数は、文字列を長整数 **(atol)** に変換します。

入力文字列は、指定された型の数値として解釈できる文字シーケンスです。 関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。 この文字は、文字列を終了する null 文字 ('\0' または L'\0') である場合があります。

**atol**の*str*引数は、次の形式になります。

> [*空白*][*記号*][*数字*] ]

*空白は*空白文字またはタブ文字で構成され、無視されます。*符号*はプラス (+) またはマイナス (-) のいずれかです。*数字*は 1 桁以上です。

**_wtol**は、ワイド文字列を取ることを除いて **、atol**と同じです。

**_l**サフィックスを持つこれらの関数のバージョンは、現在のロケールの代わりに渡された locale パラメーターを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstol**|**atol**|**atol**|**_wtol**|
|**_ttol**|**atol**|**atol**|**_wtol**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|--------------|---------------------|
|**atol**|\<stdlib.h>|
|**_atol_l**, **_wtol**, **_wtol_l**|\<stdlib.h> と \<wchar.h>|

## <a name="example"></a>例

このプログラムは **、atol**関数を使用して、文字列として格納された数値を数値に変換する方法を示します。

```C
// crt_atol.c
// This program shows how numbers stored as
// strings can be converted to numeric values
// using the atol functions.
#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    long    value = 0;

    // An example of the atol function
    // with leading and trailing white spaces.
    str = "  -2309 ";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an arbitrary decimal point.
    str = "314127.64";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );

    // Another example of the atol function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atol( str );
    printf( "Function: atol( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atol( "  -2309 " ) = -2309
Function: atol( "314127.64" ) = 314127
Function: atol( "3336402735171707160320" ) = 2147483647
Overflow condition occurred.
```

## <a name="see-also"></a>関連項目

[データ変換](../../c-runtime-library/data-conversion.md)<br/>
[浮動小数点サポート](../../c-runtime-library/floating-point-support.md)<br/>
[ロケール](../../c-runtime-library/locale.md)<br/>
[_ecvt](ecvt.md)<br/>
[_fcvt](fcvt.md)<br/>
[_gcvt](gcvt.md)<br/>
[setlocale、_wsetlocale](setlocale-wsetlocale.md)<br/>
[_atodbl、_atodbl_l、_atoldbl、_atoldbl_l、_atoflt、_atoflt_l](atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)<br/>
