---
description: '詳細については、次を参照してください: fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l'
title: fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l
ms.date: 11/04/2016
api_name:
- _fprintf_s_l
- fwprintf_s
- fprintf_s
- _fwprintf_s_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ftprintf_s
- fprintf_s
- fwprintf_s
helpviewer_keywords:
- ftprintf_s_l function
- ftprintf_s function
- _fprintf_s_l function
- _ftprintf_s function
- _ftprintf_s_l function
- fwprintf_s_l function
- fwprintf_s function
- fprintf_s_l function
- fprintf_s function
- _fwprintf_s_l function
- print formatted data to streams
ms.assetid: 16067c3c-69ce-472a-8272-9aadf1f5beed
ms.openlocfilehash: 89b597d59b9b3b42dcbd884929504f473182cb3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314160"
---
# <a name="fprintf_s-_fprintf_s_l-fwprintf_s-_fwprintf_s_l"></a>fprintf_s、_fprintf_s_l、fwprintf_s、_fwprintf_s_l

書式付きデータをストリームに出力します。 これらは、「[CRT のセキュリティ機能](../../c-runtime-library/security-features-in-the-crt.md)」の説明にあるとおり、セキュリティが強化されたバージョンの [fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md) です。

## <a name="syntax"></a>構文

```C
int fprintf_s(
   FILE *stream,
   const char *format [,
   argument_list ]
);
int _fprintf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument_list ]
);
int fwprintf_s(
   FILE *stream,
   const wchar_t *format [,
   argument_list ]
);
int _fwprintf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument_list ]
);
```

### <a name="parameters"></a>パラメーター

*一連*<br/>
**FILE** 構造体へのポインター。

*format*<br/>
書式指定文字列。

*argument_list*<br/>
書式指定文字列への省略可能な引数。

*locale*<br/>
使用するロケール。

## <a name="return-value"></a>戻り値

**fprintf_s** は、書き込まれたバイト数を返します。 **fwprintf_s** は、書き込まれたワイド文字の数を返します。 これらの関数は、出力エラーが発生した場合、負の値を返します。

## <a name="remarks"></a>解説

**fprintf_s** 書式を設定し、一連の文字と値を出力 *ストリーム* に出力します。 *Argument_list* 内の各引数 (存在する場合) は、*形式* の対応する形式指定に従って変換および出力されます。 *Format* 引数は、 [printf 関数と wprintf 関数の書式指定構文](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)を使用します。

**fwprintf_s** は **fprintf_s** のワイド文字バージョンです。 **fwprintf_s** では、 *format* はワイド文字列です。 ストリームが ANSI モードで開かれている場合、これらの関数の動作は同じになります。 **fprintf_s** は、現在 UNICODE ストリームへの出力をサポートしていません。

**_L** サフィックスを持つこれらの関数のバージョンは、現在のロケールの代わりに渡されたロケールパラメーターを使用する点を除いて同じです。

> [!IMPORTANT]
> *format* にユーザー定義の文字列を指定しないでください。

セキュリティで保護されていないバージョン (「 [fprintf、_fprintf_l、fwprintf、_fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)」を参照) と同様に、これらの関数は、「 [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、パラメーターを検証し、無効なパラメーターハンドラーを呼び出します ( *ストリーム* または *形式* のいずれかが null ポインターの場合)。 書式指定文字列自体も検証されます。 未知の書式指定子や不適切な形式の書式指定子がある場合、これらの関数は無効なパラメーター例外を生成します。 どのような場合でも、実行の継続が許可された場合、関数は-1 を返し、 **errno** を **EINVAL** に設定します。 エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftprintf_s**|**fprintf_s**|**fprintf_s**|**fwprintf_s**|
|**_ftprintf_s_l**|**_fprintf_s_l**|**_fprintf_s_l**|**_fwprintf_s_l**|

詳細については、[書式の指定](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)に関する記事をご覧ください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fprintf_s**、 **_fprintf_s_l**|\<stdio.h>|
|**fwprintf_s**、 **_fwprintf_s_l**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fprintf_s.c
// This program uses fprintf_s to format various
// data and print it to the file named FPRINTF_S.OUT. It
// then displays FPRINTF_S.OUT on the screen using the system
// function to invoke the operating-system TYPE command.

#include <stdio.h>
#include <process.h>

FILE *stream;

int main( void )
{
   int    i = 10;
   double fp = 1.5;
   char   s[] = "this is a string";
   char   c = '\n';

   fopen_s( &stream, "fprintf_s.out", "w" );
   fprintf_s( stream, "%s%c", s, c );
   fprintf_s( stream, "%d\n", i );
   fprintf_s( stream, "%f\n", fp );
   fclose( stream );
   system( "type fprintf_s.out" );
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
[sprintf、_sprintf_l、swprintf、_swprintf_l、 \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
