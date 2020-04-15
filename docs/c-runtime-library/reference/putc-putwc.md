---
title: putc、putwc
ms.date: 4/2/2020
api_name:
- putwc
- putc
- _o_putc
- _o_putwc
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _puttc
- putwc
- putc
helpviewer_keywords:
- streams, writing characters to
- characters, writing
- putwc function
- putc function
- _puttc function
- puttc function
ms.assetid: a37b2e82-9d88-4565-8190-ff8d04c0ddb9
ms.openlocfilehash: 8809595c90c48976d9f28ffa659714f5b9d919c9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338458"
---
# <a name="putc-putwc"></a>putc、putwc

ストリームに文字を書き込みます。

## <a name="syntax"></a>構文

```C
int putc(
   int c,
   FILE *stream
);
wint_t putwc(
   wchar_t c,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*C*<br/>
書き込む文字。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

書き込まれた文字を返します。 エラーまたはファイルの終わりの条件を示すには **、putc**と**putchar**は**EOF**を返します。**プットフ**と**プットチャル**は**WEOFを**返します。 4 つすべてのルーチンで、[ferror](ferror.md) または [feof](feof.md) を使用して、エラーまたはファイルの終端を確認します。 *ストリーム*に null ポインタを渡した場合は、「[パラメータの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行を続行できる場合、これらの関数は**EOF**または**WEOF**を返し **、errno**を**EINVAL**に設定します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**putc**ルーチンは、現在位置にある出力*ストリーム*に単一文字*c*を書き込みます。 任意の整数を**putc**に渡すことができますが、書き込まれるのは下位 8 ビットだけです。 **プットチャル**ルーチンは`putc( c, stdout )`と同じです。 各ルーチンでは、読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 **putc**と**putchar**はそれぞれ**fputc**と **_fputchar**に似ていますが、関数とマクロの両方として実装されています ([関数とマクロの選択を](../../c-runtime-library/recommendations-for-choosing-between-functions-and-macros.md)参照)。 **putwc**と**putwchar**はそれぞれ **、パトク**と**プットチャー**のワイド文字バージョンです。 ストリームが ANSI モードで開かれている場合 **、putwc**と**putc**は同じように動作します。 **putc**は現在 UNICODE ストリームへの出力をサポートしていません。

**_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。 詳細については、「**_putc_nolock、_putwc_nolock**」をご覧ください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_puttc**|**putc**|**putc**|**putwc**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**putc**|\<stdio.h>|
|**putwc**|\<stdio.h> または \<wchar.h>|

ユニバーサル Windows プラットフォーム (UWP) アプリでは、コンソールはサポートされていません。 コンソール **、stdin 、stdout**、および**stdout****stderr**に関連付けられている標準ストリーム ハンドルは、C ランタイム関数が UWP アプリで使用する前にリダイレクトする必要があります。 互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_putc.c
/* This program uses putc to write buffer
* to a stream. If an error occurs, the program
* stops before writing the entire buffer.
*/

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char *p, buffer[] = "This is the line of output\n";
   int  ch;

   ch = 0;
   /* Make standard out the stream and write to it. */
   stream = stdout;
   for( p = buffer; (ch != EOF) && (*p != '\0'); p++ )
      ch = putc( *p, stream );
}
```

### <a name="output"></a>出力

```Output
This is the line of output
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputc、fputwc](fputc-fputwc.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
