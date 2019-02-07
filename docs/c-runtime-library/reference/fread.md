---
title: fread
ms.date: 11/28/2018
apiname:
- fread
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
- fread
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
ms.openlocfilehash: 7248eb08409b50d855dbb70c7638a856302b345b
ms.sourcegitcommit: bd637e9c39650cfd530520ea978a22fa4caa0e42
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/07/2019
ms.locfileid: "55849972"
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

*size*<br/>
項目サイズ (バイト単位)。

*count*<br/>
読み取る項目の最大数。

*stream*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fread**可能性のあるすべてのアイテムの数が実際に読み取られた返しますより小さい*カウント*エラーが発生した場合、またはファイルの末尾が到達する前に発生した場合*カウント*します。 使用して、 **feof**または**ferror**ファイルの終わり条件からの読み取りエラーを区別するために関数。 場合*サイズ*または*カウント*は 0 です。 **fread**返します 0 と、バッファーの内容は変更されません。 場合*ストリーム*または*バッファー* null ポインターの場合は、 **fread**で説明されているように、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**は 0 を返します。

参照してください[ \_doserrno、errno、 \_sys\_errlist、および\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)これらのエラー コードの詳細についてはします。

## <a name="remarks"></a>Remarks

**Fread**関数は、最大読み取ります*カウント*の項目*サイズ*入力からのバイト*ストリーム*に保存*バッファー*. 関連付けられたファイル ポインター*ストリーム*(1 つである) 場合は実際に読み取られたバイト数でインクリメントします。 指定したストリームが開いている場合[テキスト モード](../../c-runtime-library/text-and-binary-mode-file-i-o.md)、Windows スタイルの改行が Unix 形式の改行に変換されます。 つまり、復帰と改行 (CRLF) のペアが 1 つのラインフィード (LF) 文字に置き換えられます。 この置き換えは、ファイル ポインターまたは戻り値には影響しません。 エラーが発生した場合、ファイル ポインターの位置は不確定になります。 部分的に読み取られた項目の値を特定できません。

データの量が要求された場合、テキスト モードのストリームで使用する場合 (つまり、*サイズ* \* *カウント*) 内部以上**ファイル** \*バッファー サイズ (既定では 4096 (バイト単位) を使用して構成可能な[setvbuf](../../c-runtime-library/reference/setvbuf.md)) をユーザー指定のバッファーに直接ストリームのデータをコピーし、そのバッファーで改行の変換が行われる、します。 変換後のデータは過去のデータのバッファーにコピーされたストリーム データよりも短い場合があるため*バッファー*\[*return_value* \* *サイズ*] (場所*return_value*からの戻り値は、 **fread**) ファイルから変換されていないデータを含めることができます。 このため、お勧めする null で終了で文字データ*バッファー*\[*return_value* \* *サイズ*]、バッファーの目的がある場合C スタイル文字列として機能します。 参照してください[fopen](fopen-wfopen.md)テキスト モードとバイナリ モードの影響の詳細について。

この関数は他のスレッドをロックします。 ロックしないバージョンが必要な場合を使用して、 **_fread_nolock**します。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
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
[テキスト モードとバイナリ ファイル入出力](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
