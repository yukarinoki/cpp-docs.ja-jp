---
title: fgetc、fgetwc
ms.date: 11/04/2016
apiname:
- fgetwc
- fgetc
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _fgettc
- fgetwc
- fgetc
helpviewer_keywords:
- fgettc function
- characters, reading
- _fgettc function
- fgetc function
- streams, reading characters from
- reading characters from streams
- fgetwc function
ms.assetid: 13348b7b-dc86-421c-9d6c-611ca79c8338
ms.openlocfilehash: a853a46fc43106c9ea57be84b37fb46a18041ba8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62334009"
---
# <a name="fgetc-fgetwc"></a>fgetc、fgetwc

ストリームから単一の文字を読み取ります。

## <a name="syntax"></a>構文

```C
int fgetc(
   FILE *stream
);
wint_t fgetwc(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*stream*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fgetc**として読み取られた文字を返します、 **int**返しますまたは**EOF**エラーまたはファイルの終わりを示します。 **fgetwc**から制御が戻るとして、 [wint_t](../../c-runtime-library/standard-types.md)、ワイド文字を読み取る文字に対応する値または**WEOF**エラーまたはファイルの終わりを示します。 両方の関数を使用して、 **feof**または**ferror**エラーと、ファイルの終わり条件とを区別します。 読み取りエラーが発生すると、ストリームのエラー インジケーターが設定されます。 場合*ストリーム*は**NULL**、 **fgetc**と**fgetwc** 」の説明に従って、無効なパラメーター ハンドラーを呼び出す[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**戻って**EOF**します。

## <a name="remarks"></a>Remarks

関連付けられているファイルの現在位置から 1 つの文字を読み取りますこれらの各関数*ストリーム*します。 関数は、次の文字 (定義されている場合) を指すように、関連ファイルのポインターをインクリメントします。 ストリームがファイルの末尾にある場合、ストリームのファイルの末尾を示すインジケーターが設定されます。

**fgetc**と等価**getc**関数とマクロではなく関数としてのみ実装されます。

**fgetwc**のワイド文字バージョンは、 **fgetc**; 読み取り**c**マルチバイト文字またはワイド文字かどうかに従ってとして*ストリーム*で開くテキスト モードまたはバイナリ モードの場合は。

**_nolock** サフィックスが付いているバージョンは同じものですが、他のスレッドによる干渉から保護されない点が異なります。

テキスト モードとバイナリ モードのワイド文字とマルチバイト文字の処理の詳細については、「[Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md)」 (テキスト モードとバイナリ モードの Unicode ストリーム入出力) を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_fgettc**|**fgetc**|**fgetc**|**fgetwc**|

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**fgetc**|\<stdio.h>|
|**fgetwc**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fgetc.c
// This program uses getc to read the first
// 80 input characters (or until the end of input)
// and place them into a string named buffer.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   FILE *stream;
   char buffer[81];
   int  i, ch;

   // Open file to read line from:
   fopen_s( &stream, "crt_fgetc.txt", "r" );
   if( stream == NULL )
      exit( 0 );

   // Read in first 80 characters and place them in "buffer":
   ch = fgetc( stream );
   for( i=0; (i < 80 ) && ( feof( stream ) == 0 ); i++ )
   {
      buffer[i] = (char)ch;
      ch = fgetc( stream );
   }

   // Add null to end string
   buffer[i] = '\0';
   printf( "%s\n", buffer );
   fclose( stream );
}
```

## <a name="input-crtfgetctxt"></a>入力: crt_fgetc.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
Line one.
Line two.
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fputc、fputwc](fputc-fputwc.md)<br/>
[getc、getwc](getc-getwc.md)<br/>
