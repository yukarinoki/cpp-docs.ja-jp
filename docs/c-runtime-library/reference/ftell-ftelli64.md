---
title: ftell、_ftelli64
ms.date: 4/2/2020
api_name:
- _ftelli64
- ftell
- _o__ftelli64
- _o_ftell
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
- _ftelli64
- ftell
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
ms.openlocfilehash: bfe79610161a7f4032517d9f7eaa0de50be18e50
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345623"
---
# <a name="ftell-_ftelli64"></a>ftell、_ftelli64

ファイル ポインターの現在の位置を取得します。

## <a name="syntax"></a>構文

```C
long ftell(
   FILE *stream
);
__int64 _ftelli64(
   FILE *stream
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
ターゲット**ファイル**構造。

## <a name="return-value"></a>戻り値

**ftell**と **_ftelli64**現在のファイル位置を返します。 テキスト モードでは復帰改行の変換が行われるため **、ftell**および **_ftelli64**によって返される値は、テキスト モードで開かれたストリームの物理バイト オフセットを反映しない場合があります。 fseek と[fseek](fseek-fseeki64.md) **ftell**を使用するか[、_fseeki64](fseek-fseeki64.md)を指定して **_ftelli64**を使用して、ファイルの場所に正しく戻ります。 エラーが発生すると **、ftell**と **_ftelli64**は、パラメーター[の検証](../../c-runtime-library/parameter-validation.md)で説明されているように、無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は -1L を返し、ERRNO で定義された 2 つの定数のいずれかに**errno**を設定します。H。 **EBADF**定数は、*ストリーム*引数が有効なファイル・ポインター値でないか、オープン・ファイルを参照していないことを示します。 **EINVAL**は、無効な*ストリーム*引数が関数に渡されたことを意味します。 シークできないデバイス (端末やプリンターなど) で、または*ストリーム*がオープン・ファイルを参照していない場合、戻り値は未定義です。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**ftell**関数と **_ftelli64**関数は、 *stream*に関連付けられているファイル ポインタの現在位置を取得します。 位置は、ストリームの先頭を基準としたオフセットとして表されます。

データを追加するためにファイルを開く場合、現在のファイルの位置は、次の書き込みが発生する場所ではなく最後の I/O 操作によって決まります。 たとえば、追加のためにファイルが開かれ、最後の操作が読み取りだった場合、ファイルの位置は、次の書き込みが開始される位置ではなく、次の読み取り操作が開始される位置になります  (ファイルを追加用に開くと、ファイル位置は書き込み操作の前にファイルの末尾に移動されます。追加用に開かれたファイルに対して I/O 操作がまだ発生していない場合、ファイル位置はファイルの先頭になります。

テキスト モードでは、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取り/書き込み用に開かれたファイルでは **、fopen**と関連するすべてのルーチンがファイルの末尾に Ctrl + Z があるかどうかをチェックし、可能であれば削除します。 これは **、ftell**と[fseek](fseek-fseeki64.md)または **_ftelli64**と[_fseeki64](fseek-fseeki64.md)の組み合わせを使用して、Ctrl + Z で終わるファイル内を移動すると **、ftell**または **_ftelli64**がファイルの末尾付近で不適切に動作する可能性があるためです。

この関数は実行中に呼び出し元スレッドをロックするため、スレッド セーフです。 ロックされていないバージョンについては **、「_ftell_nolock」** を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|省略可能なヘッダー|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_ftell.c
// This program opens a file named CRT_FTELL.C
// for reading and tries to read 100 characters. It
// then uses ftell to determine the position of the
// file pointer and displays this position.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long position;
   char list[100];
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )
   {
      // Move the pointer by reading data:
      fread( list, sizeof( char ), 100, stream );
      // Get position after read:
      position = ftell( stream );
      printf( "Position after trying to read 100 bytes: %ld\n",
              position );
      fclose( stream );
   }
}
```

```Output
Position after trying to read 100 bytes: 100
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[fgetpos](fgetpos.md)<br/>
[fseek、_fseeki64](fseek-fseeki64.md)<br/>
[_lseek、_lseeki64](lseek-lseeki64.md)<br/>
