---
title: setvbuf
ms.date: 11/04/2016
apiname:
- setvbuf
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
- setvbuf
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
ms.openlocfilehash: d4336c6cc478a035fcc0b9b059a7161d58bc4442
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62356317"
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

*stream*<br/>
**FILE** 構造体へのポインター。

*バッファー*<br/>
ユーザー割り当てのバッファー。

*モード*<br/>
バッファリングのモード。

*size*<br/>
バイト単位のバッファー サイズ。 許容範囲:2 < =*サイズ*< = INT_MAX (2147483647)。 指定された値では内部的には、*サイズ*は最も近い 2 の倍数に切り下げ。

## <a name="return-value"></a>戻り値

処理が正常に終了した場合は 0 を返します。

場合*ストリーム*は**NULL**、または*モード*または*サイズ*は」の説明に従って有効な変更ではなく、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行が続行すると、この関数は-1 を返し、セットを許可された場合**errno**に**EINVAL**します。

エラー コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**Setvbuf**関数により、両方のバッファリングを制御し、バッファーのサイズをプログラム*ストリーム*します。 *ストリーム*開かれた後に、I/O 操作を実施されていませんが、開いているファイルを参照する必要があります。 によって示される配列*バッファー*である場合を除き、バッファーとして使用されます**NULL**その場合、 **setvbuf**が自動的に割り当てられたバッファーの長さを使用して*サイズ*/2 \* 2 バイト。

モードである必要があります **_IOFBF**、 **_IOLBF**、または **_IONBF**します。 場合*モード*は **_IOFBF**または **_IOLBF**、し*サイズ*バッファーのサイズとして使用されます。 場合*モード*は **_IONBF**、ストリームはバッファー処理されず、*サイズ*と*バッファー*は無視されます。 値を*モード*とその意味。

|*モード*値|説明|
|-|-|
| **_IOFBF** | フル バッファリングします。つまり、*バッファー*バッファーとして提供されると*サイズ*バッファーのサイズとして使用されます。 場合*バッファー*は**NULL**が自動的に割り当てられたバッファー*サイズ*バイト長を使用します。 |
| **_IOLBF** | 一部のシステムでは、行バッファリングします。 ただし、win32 の動作は同じ **_IOFBF** -フル バッファリングします。 |
| **_IONBF** | 使用に関係なく、バッファーがない*バッファー*または*サイズ*します。 |

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**setvbuf**|\<stdio.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
