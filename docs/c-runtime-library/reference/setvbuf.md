---
title: setvbuf
ms.date: 4/2/2020
api_name:
- setvbuf
- _o_setvbuf
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
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: 203265a8dd85854bcedd737359b856fdc4cce04d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81316259"
---
# <a name="setvbuf"></a>setvbuf

ストリームのバッファリングとバッファー サイズを制御します。

## <a name="syntax"></a>構文

```C
int setvbuf(
   FILE *stream,
   char *buffer,
   int mode,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*ストリーム*<br/>
**FILE** 構造体へのポインター。

*バッファー*<br/>
ユーザー割り当てのバッファー。

*モード*<br/>
バッファリングのモード。

*サイズ*<br/>
バイト単位のバッファー サイズ。 許容範囲: 2 <=*サイズ*<= INT_MAX (2147483647)。 内部的には、*サイズ*に対して指定された値は、最も近い 2 の倍数に切り捨てられます。

## <a name="return-value"></a>戻り値

処理が正常に終了した場合は 0 を返します。

*stream*が**NULL**の場合、または*モード*または*サイズ*が有効な変更の範囲内にない場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行の継続が許可された場合、この関数は -1 を返し、**errno** を **EINVAL** に設定します。

これらと他のエラー コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**setvbuf**関数を使用すると、プログラムは *、ストリーム*のバッファリングとバッファ サイズの両方を制御できます。 *ストリーム*は、開かれた後に I/O 操作を行っていないオープン・ファイルを参照する必要があります。 *buffer*によって指される配列は **、NULL**でない限りバッファとして使用され、その場合**setvbuf**は長*さサイズ*/2 2\*バイトのバッファを自動的に割り当てます。

モードは、 **_IOFBF**、 **_IOLBF**、または **_IONBF**である必要があります。 *mode*が **_IOFBF**または **_IOLBF**の場合 *、size*がバッファーのサイズとして使用されます。 *mode*が **_IONBF**の場合、ストリームはバッファリングされず、*サイズ*と*バッファー*は無視されます。 *モード*の値とその意味は次のとおりです。

|*モード*値|意味|
|-|-|
| **_IOFBF** | フル バッファリング。つまり、*バッファー*はバッファーとして使用され、*サイズ*はバッファーのサイズとして使用されます。 *buffer*が**NULL**の場合は、自動的に割り当てられたバッファー *・サイズ*のバイト長が使用されます。 |
| **_IOLBF** | 一部のシステムでは、行バッファリングします。 ただし、Win32 の場合、動作は **_IOFBF** - フル バッファリングと同じです。 |
| **_IONBF** | バッファや*サイズ*に関係なく、*バッファ*は使用されません。 |

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example"></a>例

```C
// crt_setvbuf.c
// This program opens two streams: stream1
// and stream2. It then uses setvbuf to give stream1 a
// user-defined buffer of 1024 bytes and stream2 no buffer.
//

#include <stdio.h>

int main( void )
{
   char buf[1024];
   FILE *stream1, *stream2;

   if( fopen_s( &stream1, "data1", "a" ) == 0 &&
       fopen_s( &stream2, "data2", "w" ) == 0 )
   {
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )
         printf( "Incorrect type or size of buffer for stream1\n" );
      else
         printf( "'stream1' now has a buffer of 1024 bytes\n" );
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )
         printf( "Incorrect type or size of buffer for stream2\n" );
      else
         printf( "'stream2' now has no buffer\n" );
      _fcloseall();
   }
}
```

```Output
'stream1' now has a buffer of 1024 bytes
'stream2' now has no buffer
```

## <a name="see-also"></a>関連項目

[ストリーム入出力](../../c-runtime-library/stream-i-o.md)<br/>
[fclose、_fcloseall](fclose-fcloseall.md)<br/>
[fflush](fflush.md)<br/>
[fopen、_wfopen](fopen-wfopen.md)<br/>
[setbuf](setbuf.md)<br/>
