---
title: ftell、_ftelli64 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d09d29abc4d1406bd85187ceb5c6661be98229be
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402441"
---
# <a name="ftell-ftelli64"></a>ftell、_ftelli64

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
ターゲット**ファイル**構造体。

## <a name="return-value"></a>戻り値

**ftell**と **_ftelli64**ファイルの現在の位置を返します。 によって返される値**ftell**と **_ftelli64**キャリッジ リターンとライン フィードの変換のため、テキスト モードで開いたストリームの物理バイト オフセットを表さない場合があります。 使用して**ftell**で[fseek](fseek-fseeki64.md)または **_ftelli64**で[_fseeki64](fseek-fseeki64.md)正しくファイルの場所に戻ります。 エラーが発生した**ftell**と **_ftelli64** 」の説明に従って、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の続行には、これらの関数の戻り値-1 L セットが許可された場合**errno** ERRNO で定義されている 2 つの定数のいずれかにします。H. **EBADF**定数、*ストリーム*引数が有効なファイル ポインター値ではないまたは開いているファイルを参照していません。 **EINVAL** 、無効なことを意味*ストリーム*関数に引数が渡されました。 デバイス (端末やプリンターなど)、シークできない場合や*ストリーム*参照していない、開いているファイルを戻り値が定義されていません。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

**Ftell**と **_ftelli64**関数に関連付けられたファイル ポインター (存在する場合) の現在の位置を取得する*ストリーム*です。 位置は、ストリームの先頭を基準としたオフセットとして表されます。

データを追加するためにファイルを開く場合、現在のファイルの位置は、次の書き込みが発生する場所ではなく最後の I/O 操作によって決まります。 たとえば、追加のためにファイルが開かれ、最後の操作が読み取りだった場合、ファイルの位置は、次の書き込みが開始される位置ではなく、次の読み取り操作が開始される位置になります  (追加のためにファイルが開かれるときには、ファイルの位置は書き込み操作が開始される前にファイルの末尾に移動されます)。追加のために開かれたファイルで I/O 操作がまだ発生していない場合、ファイルの位置はファイルの先頭です。

テキスト モードでは、Ctrl + Z は入力時に EOF (end-of-file) 文字として解釈されます。 読み取り/書き込み用に開かれたファイルで**fopen**関連するすべてのルーチンは、ファイルの末尾に CTRL + Z を確認して、可能であればそれを削除します。 これはの組み合わせを使用して、 **ftell**と[fseek](fseek-fseeki64.md)または **_ftelli64**と[_fseeki64](fseek-fseeki64.md)で終わるファイル内で移動するにはCTRL + Z が発生する可能性があります**ftell**または **_ftelli64**が、ファイルの末尾付近に正しく動作します。

この関数は実行中に呼び出し元スレッドをロックするため、スレッド セーフです。 ロックしないバージョンでは、次を参照してください。 **_ftell_nolock**です。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|省略可能なヘッダー|
|--------------|---------------------|----------------------|
|**ftell**|\<stdio.h>|\<errno.h>|
|**_ftelli64**|\<stdio.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
