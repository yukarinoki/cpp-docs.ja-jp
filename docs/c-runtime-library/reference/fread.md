---
description: '詳細情報: fread'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 131dacd296d4e710ea1b91d9a8578ef06b76a341
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314049"
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

*格納*<br/>
データの格納場所。

*size*<br/>
項目サイズ (バイト単位)。

*count*<br/>
読み取る項目の最大数。

*一連*<br/>
**FILE** 構造体へのポインター。

## <a name="return-value"></a>戻り値

**fread** は、実際に読み取られた完全な項目の数を返します。エラーが発生した場合、またはファイルの末尾が *カウント* に到達する前に検出された場合は、 *count* よりも小さくなることがあります。 Read エラーをファイルの終端の条件と区別するには、 **feof** 関数または **ferror** 関数を使用します。 *Size* または *count* が0の場合、 **fread** は0を返し、バッファーの内容は変更されません。 *ストリーム* または *バッファー* が null ポインターの場合、 **fread** は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **errno** を **EINVAL** に設定し、0を返します。

これらのエラーコードの詳細については[ \_ 、「doserrno、errno、 \_ sys \_ errlist、および \_ sys \_ nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 」を参照してください。

## <a name="remarks"></a>解説

**Fread** 関数は、入力 *ストリーム* から *サイズ* バイトの項目 *数* を読み取り、*バッファー* に格納します。 *ストリーム* に関連付けられているファイルポインター (存在する場合) は、実際に読み取られたバイト数によって増加します。 指定されたストリームが [テキストモード](../../c-runtime-library/text-and-binary-mode-file-i-o.md)で開かれている場合、Windows スタイルの改行は Unix スタイルの改行に変換されます。 つまり、キャリッジリターンラインフィード (CRLF) のペアは、単一行フィード (LF) 文字に置き換えられます。 この置き換えは、ファイル ポインターまたは戻り値には影響しません。 エラーが発生した場合、ファイル ポインターの位置は不確定になります。 部分的に読み取られた項目の値を特定できません。

テキストモードストリームで使用する場合、要求されたデータの量 (*サイズ* \* ) が内部 **ファイル** の \* バッファーサイズ以上 (既定では、4096バイトで、 [setvbuf](../../c-runtime-library/reference/setvbuf.md)を使用して構成できます)、ストリームデータはユーザー指定のバッファーに直接コピーされ、そのバッファーで改行変換が行われます。 変換されたデータはバッファーにコピーされたストリームデータよりも短い可能性があるので、データが *バッファー* \[ *return_value* \* *サイズ*] ( *return_value* は **fread** からの戻り値) である場合がありますが、ファイルから変換されていないデータが含まれている可能性があります。 このため、  \[  \* バッファーの目的が C スタイルの文字列として機能する場合は、バッファーの return_value *サイズ*] で null 値を終了することをお勧めします。 テキストモードとバイナリモードの効果の詳細については、「 [fopen](fopen-wfopen.md) 」を参照してください。

この関数は他のスレッドをロックします。 ロックしないバージョンが必要な場合は、 **_fread_nolock** を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>要件

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
[テキストファイルとバイナリファイル i/o](../../c-runtime-library/text-and-binary-mode-file-i-o.md)<br/>
[fopen](fopen-wfopen.md)<br/>
[fwrite](fwrite.md)<br/>
[_read](read.md)<br/>
