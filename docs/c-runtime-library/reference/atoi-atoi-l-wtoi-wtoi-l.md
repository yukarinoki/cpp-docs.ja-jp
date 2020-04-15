---
title: atoi、_atoi_l、_wtoi、_wtoi_l
ms.date: 4/2/2020
api_name:
- _wtoi
- _wtoi_l
- atoi
- _atoi_l
- _o__atoi_l
- _o__wtoi
- _o__wtoi_l
- _o_atoi
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
- _tstoi
- _wtoi
- _ttoi
- atoi
- _atoi_l
- _wtoi_l
helpviewer_keywords:
- _atoi_l function
- ttoi function
- atoi_l function
- string conversion, to integers
- _wtoi function
- wtoi_l function
- tstoi function
- _ttoi function
- _tstoi function
- _wtoi_l function
- atoi function
- wtoi function
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
ms.openlocfilehash: ef65f8986cf02b6385cbce71e5e81fa690b38b2e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348868"
---
# <a name="atoi-_atoi_l-_wtoi-_wtoi_l"></a>atoi、_atoi_l、_wtoi、_wtoi_l

文字列を整数に変換します。

## <a name="syntax"></a>構文

```C
int atoi(
   const char *str
);
int _wtoi(
   const wchar_t *str
);
int _atoi_l(
   const char *str,
   _locale_t locale
);
int _wtoi_l(
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

各関数は、入力文字を数値として解釈することによって生成された**int**値を返します。 **atoi**の場合は 0 **_wtoi、** 入力をその型の値に変換できない場合は、戻り値は 0 です。

大きな負の整数値でオーバーフローした場合 **、LONG_MIN**が返されます。 **これらの条件に**関すると**INT_MIN**を返 _wtoi **INT_MAX****す**。 範囲外の場合は **、errno**が**ERANGE**に設定されます。 渡されたパラメーターが**NULL**の場合は、「パラメーター[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、0 を返します。

## <a name="remarks"></a>解説

これらの関数は、文字列を整数値 (**atoi**および **_wtoi**) に変換します。 入力文字列は、指定された型の数値として解釈できる文字シーケンスです。 関数は、数値の一部として認識できない文字に最初に遭遇した時点で入力文字列の読み取りを停止します。 この文字は、文字列を終了する null 文字 ('\0' または L'\0') である場合があります。

**atoi**および **_wtoi**への*str*引数は、次の形式になります。

> [*空白*][*記号*][*数字*] ]

*空白は*空白文字またはタブ文字で構成され、無視されます。*符号*はプラス (+) またはマイナス (-) のいずれかです。*数字*は 1 桁以上です。

**_l**サフィックスを持つこれらの関数のバージョンは、現在のロケールの代わりに渡された locale パラメーターを使用する点を除いて同じです。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tstoi**|**atoi**|**atoi**|**_wtoi**|
|**_ttoi**|**atoi**|**atoi**|**_wtoi**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|--------------|---------------------|
|**atoi**|\<stdlib.h>|
|**_atoi_l**, **_wtoi**, **_wtoi_l**|\<stdlib.h> または \<wchar.h>|

## <a name="example"></a>例

このプログラムは、文字列として格納された数値を**atoi**関数を使用して数値に変換する方法を示します。

```C
// crt_atoi.c
// This program shows how numbers
// stored as strings can be converted to
// numeric values using the atoi functions.

#include <stdlib.h>
#include <stdio.h>
#include <errno.h>

int main( void )
{
    char    *str = NULL;
    int     value = 0;

    // An example of the atoi function.
    str = "  -2309 ";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function.
    str = "31412764";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );

    // Another example of the atoi function
    // with an overflow condition occurring.
    str = "3336402735171707160320";
    value = atoi( str );
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );
    if (errno == ERANGE)
    {
       printf("Overflow condition occurred.\n");
    }
}
```

```Output
Function: atoi( "  -2309 " ) = -2309
Function: atoi( "31412764" ) = 31412764
Function: atoi( "3336402735171707160320" ) = 2147483647
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
