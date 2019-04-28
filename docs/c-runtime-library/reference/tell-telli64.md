---
title: _tell、_telli64
ms.date: 11/04/2016
apiname:
- _telli64
- _tell
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
- tell
- telli64
- _telli64
- _tell
helpviewer_keywords:
- tell function
- file pointers [C++], getting
- _tell function
- file pointers [C++]
- telli64 function
- _telli64 function
ms.assetid: 1500e8f9-8fec-4253-9eec-ec66125dfc9b
ms.openlocfilehash: 628f37d3b8a39a75fb2329a1b2805426f15e821f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62258573"
---
# <a name="tell-telli64"></a>_tell、_telli64

ファイル ポインターの位置を取得します。

## <a name="syntax"></a>構文

```C
long _tell(
   int handle
);
__int64 _telli64(
   int handle
);
```

### <a name="parameters"></a>パラメーター

*handle*<br/>
開いているファイルを参照するファイル記述子。

## <a name="return-value"></a>戻り値

ファイル ポインターの現在の位置。 シーク非対応のデバイスでは、戻り値は未定義です。

-1 L の戻り値は、エラーを示します。 場合*処理*は、無効なファイル記述子で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EBADF** -1 L を返します。

戻り値の詳細については、「 [_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) 」を参照してください。

## <a name="remarks"></a>Remarks

**_Tell**関数に関連付けられたファイル ポインター (存在する場合) の現在位置を取得、*処理*引数。 位置は、ファイルの先頭からのバイト数で表されます。 **_Telli64**関数では、この値は 64 ビット整数として表されます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_tell**、 **_telli64**|\<io.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_tell.c
// This program uses _tell to tell the
// file pointer position after a file read.
//

#include <io.h>
#include <stdio.h>
#include <fcntl.h>
#include <share.h>
#include <string.h>

int main( void )
{
   int  fh;
   char buffer[500];

   if ( _sopen_s( &fh, "crt_tell.txt", _O_RDONLY, _SH_DENYNO, 0) )
   {
      char buff[50];
      _strerror_s( buff, sizeof(buff), NULL );
      printf( buff );
      exit( -1 );
   }

   if( _read( fh, buffer, 500 ) > 0 )
      printf( "Current file position is: %d\n", _tell( fh ) );
   _close( fh );
}
```

### <a name="input-crttelltxt"></a>入力: crt_tell.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
Current file position is: 20
```

## <a name="see-also"></a>関連項目

[下位入出力](../../c-runtime-library/low-level-i-o.md)<br/>
[ftell、_ftelli64](ftell-ftelli64.md)<br/>
[_lseek、_lseeki64](lseek-lseeki64.md)<br/>
