---
title: fread
ms.date: 4/2/2020
api_name:
- fread
- _o_fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 26ffd56072f1a5fddc3131a42cd47c145e437b60
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81346062"
---
# <a name="fread"></a>fread

ストリームからデータを読み取ります。

## <a name="syntax"></a>構文

```C
size_t fread(
   void *buffer,
   size_t size,
   size_t count,
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*バッファー*<br/>
データの格納場所。

*サイズ*<br/>
項目サイズ (バイト単位)。

*count*<br/>
読み取る項目の最大数。

*ストリーム*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fread**は実際に読み取られた項目の数を返しますが、これはエラーが発生*した場合や*、カウントに達する前にファイルの末尾が検出された場合は *、カウント*より少なくなる可能性があります。 **feof**関数または**ferror**関数を使用して、読み取りエラーとファイル終了条件を区別します。 *size*または*count*が 0 の場合 **、fread**は 0 を返し、バッファーの内容は変更されません。 *ストリーム*または*バッファー*が null ポインターの場合は **、fread**は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、この関数は**errno**を**EINVAL**に設定し、0 を返します。

これらのエラー コードの詳細については[\_\_、doserrno、errno、sys\_errlist、および\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)を参照してください。

## <a name="remarks"></a>解説

**fread**関数は、入力*ストリーム*から*サイズの*バイトの項目を*カウント*するために読み取り、*それらを buffer*に格納します。 *ストリーム*に関連付けられたファイル ポインタ (ある場合) は、実際に読み込まれるバイト数だけ増加します。 指定されたストリームが[テキスト モード](../../c-runtime-library/text-and-binary-mode-file-i-o.md)で開かれている場合、Windows スタイルの改行は Unix スタイルの改行に変換されます。 つまり、キャリッジ リターンライン フィード (CRLF) ペアは、単一の改行 (LF) 文字に置き換えられます。 この置き換えは、ファイル ポインターまたは戻り値には影響しません。 エラーが発生した場合、ファイル ポインターの位置は不確定になります。 部分的に読み取られた項目の値を特定できません。

テキスト モード ストリームで使用する場合、要求されたデータ量 (つまり、*サイズ*\**カウント*) が内部**FILE**\*バッファ サイズ以上 (既定では[setvbuf](../../c-runtime-library/reference/setvbuf.md)を使用して構成可能な 4096 バイト)、ストリーム データはユーザー指定のバッファに直接コピーされ、改行変換はそのバッファで行われます。 変換されたデータはバッファにコピーされたストリームデータよりも短い場合があるため、*バッファ*\[*return_value*\**サイズ*]を過ぎて*return_valueは***、** ファイルから変換されていないデータを含めることができます。 このため、バッファーの意図が C スタイルの文字列として機能する場合は、 バッファー\[*return_value* \* *サイズ*]*で文字*データを null 終了することをお勧めします。 テキストモードとバイナリモードの効果の詳細については[、fopen](fopen-wfopen.md)を参照してください。

この関数は他のスレッドをロックします。 ロックされていないバージョンが必要な場合は **、_fread_nolock**を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**fread**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_fread.c
// This program opens a file named FREAD.OUT and
// writes 25 characters to the file. It then tries to open
// FREAD.OUT and read in 25 characters. If the attempt succeeds,
// the program displays the number of actual items read.

#include <stdio.h>

int main( void )
{
   FILE *stream;
   char list[30];
   int  i, numread, numwritten;

   // Open file in text mode:
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )
   {
      for ( i = 0; i < 25; i++ )
         list[i] = (char)('z' - i);
      // Write 25 characters to stream
      numwritten = fwrite( list, sizeof( char ), 25, stream );
      printf( "Wrote %d items\n", numwritten );
      fclose( stream );

   }
   else
      printf( "Problem opening the file\n" );

   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )
   {
      // Attempt to read in 25 characters
      numread = fread( list, sizeof( char ), 25, stream );
      printf( "Number of items read = %d\n", numread );
      printf( "Contents of buffer = %.25s\n", list );
      fclose( stream );
   }
   else
      printf( "File could not be opened\n" );
}
```

```Output
Wrote 25 items
Number of items read = 25
Contents of buffer = zyxwvutsrqponmlkjihgfedcb
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[テキストおよびバイナリ ファイル I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
