---
title: fprintf、_fprintf_l、fwprintf、_fwprintf_l
ms.date: 11/04/2016
apiname:
- fwprintf
- fprintf
- _fprintf_l
- _fwprintf_l
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
apitype: DLLExport
f1_keywords:
- fprintf
- fwprintf
- _ftprintf
helpviewer_keywords:
- _fwprintf_l function
- fprintf function
- fprintf_l function
- _fprintf_l function
- _ftprintf function
- fwprintf function
- ftprintf_l function
- ftprintf function
- _ftprintf_l function
- print formatted data to streams
- fwprintf_l function
ms.assetid: 34a87e1c-6e4d-4d48-a611-58314dd4dc4b
ms.openlocfilehash: d84ef50e6fd522e393bb87664fb1eb47f3d32bb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637298"
---
# <a name="fprintf-fprintfl-fwprintf-fwprintfl"></a>fprintf、_fprintf_l、fwprintf、_fwprintf_l

書式付きデータをストリームに出力します。 これらの関数のセキュリティを強化したバージョンを使用できます。「[fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)」をご覧ください。

## <a name="syntax"></a>構文

```C
int fprintf(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fprintf_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwprintf(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwprintf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*format*<br/>
書式指定文字列。

*argument*<br/>
省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**fprintf**書き込まれたバイト数を返します。 **fwprintf**書き込まれたワイド文字の数を返します。 これらの関数は、出力エラーが発生した場合、負の値を返します。 場合*ストリーム*または*形式*は**NULL**、」の説明に従って、これらの関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合、関数は-1 を返し設定と**errno**に**EINVAL**します。 使用する場合は、有効な書式設定文字の書式指定文字列がチェックされません**fprintf_s**または**fwprintf_s**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**fprintf**書式化して、一連の文字や、出力値を出力*ストリーム*します。 各関数*引数*(ある場合) は変換されに対応する書式指定に応じて*形式*します。 **Fprintf**、*形式*引数が同じ構文と使用ができるように**printf**します。

**fwprintf**のワイド文字バージョンは、 **fprintf**、 **fwprintf**、*形式*はワイド文字列です。 ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。 **fprintf** UNICODE ストリームへ現在出力をサポートしません。

これらの関数のバージョン、 **_l**現在のスレッド ロケールの代わりに渡されたロケール パラメーターを使用する点を除いて、サフィックスは同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf**|**fprintf**|**fprintf**|**fwprintf**|
|**_ftprintf_l**|**_fprintf_l**|**_fprintf_l**|**_fwprintf_l**|

詳細については、「 [printf 関数と wprintf 関数の書式指定フィールド](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fprintf**、 **_fprintf_l**|\<stdio.h>|
|**fwprintf**、 **_fwprintf_l**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fprintf.c
/* This program uses fprintf to format various
* data and print it to the file named FPRINTF.OUT. It
* then displays FPRINTF.OUT on the screen using the system
* function to invoke the operating-system TYPE command.
*/

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf.out", "w" );
   fprintf( stream, "%s%c", s, c );
   fprintf( stream, "%d\n", i );
   fprintf( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf.out" );
}
```

```Output
this is a string
10
1.500000
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[_cprintf、_cprintf_l、_cwprintf、_cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fscanf、_fscanf_l、fwscanf、_fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[sprintf、_sprintf_l、swprintf、_swprintf_l、\__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[書式指定構文: printf 関数と wprintf 関数](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
