---
title: realloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
dev_langs:
- C++
helpviewer_keywords:
- _brealloc function
- realloc function
- nrealloc function
- frealloc function
- _nrealloc function
- memory blocks, reallocating
- memory, reallocating
- _frealloc function
- reallocate memory blocks
ms.assetid: 2b2239de-810b-4b11-9438-32ab0a244185
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 6452d14e0a8630c68d5e179fd94d531db1b667ab
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32408095"
---
# <a name="realloc"></a>realloc

メモリ ブロックを再割り当てします。

## <a name="syntax"></a>構文

```C
void *realloc(
   void *memblock,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*_expand*<br/>
以前に割り当てられたメモリ ブロックへのポインター。

*size*<br/>
新しいサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

**realloc**を返します、 **void**再割り当てされた (移動された可能性のある) メモリ ブロックへのポインター。

指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合、元のブロックは変更されず、および**NULL**が返されます。

場合*サイズ*が 0 の場合、ブロックが指す *_expand*解放されています戻り値は**NULL**、および *_expand*指したで、。ブロックを解放します。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 以外の型へのポインターを取得する**void**型、戻り値のキャストを使用します。

## <a name="remarks"></a>コメント

**Realloc**関数は、割り当てられたメモリ ブロックのサイズを変更します。 *_Expand*引数がメモリ ブロックの先頭を指します。 場合 *_expand*は**NULL**、 **realloc**と同様に動作**malloc**し、新しいブロックを割り当てます*サイズ*バイトです。 場合 *_expand*は**NULL**、前回の呼び出しによって返されたポインターである必要があります**calloc**、 **malloc**、または**realloc**.

*サイズ*引数は、ブロックの新しいサイズをバイトで示します。 新旧のサイズのうち、小さい方のブロックの内容は変更されませんが、新しいブロックの場所は異なる場合があります。 新しいブロックできるので、新しいメモリの場所に、によって返されるポインター **realloc**を通じて渡されるポインターであるとは限りません、 *_expand*引数。 **realloc**は 0 ではありません、新しく割り当てられたメモリ バッファーが拡張の場合。

**realloc**設定**errno**に**ENOMEM**メモリの割り当てが失敗するか、要求されたメモリ量を超えています **_HEAP_MAXREQ**です。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**realloc**呼び出し**malloc** 、C++ を使用するために[_set_new_mode](set-new-mode.md)新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)です。 既定では、 **malloc**メモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドすることができるようにときに、 **realloc** 、メモリの割り当てに失敗する**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗します。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

C ランタイム ライブラリのデバッグ バージョンとリンクするアプリケーション**realloc**に解決される[_realloc_dbg](realloc-dbg.md)です。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

**realloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`関数が、グローバル変数を変更することが保証され、返されるポインターがエイリアス化されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**realloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_realloc.c
// This program allocates a block of memory for
// buffer and then uses _msize to display the size of that
// block. Next, it uses realloc to expand the amount of
// memory used by buffer and then calls _msize again to
// display the new amount of memory allocated to buffer.

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>

int main( void )
{
   long *buffer, *oldbuffer;
   size_t size;

   if( (buffer = (long *)malloc( 1000 * sizeof( long ) )) == NULL )
      exit( 1 );

   size = _msize( buffer );
   printf_s( "Size of block after malloc of 1000 longs: %u\n", size );

   // Reallocate and show new size:
   oldbuffer = buffer;     // save pointer in case realloc fails
   if( (buffer = realloc( buffer, size + (1000 * sizeof( long )) ))
        ==  NULL )
   {
      free( oldbuffer );  // free original block
      exit( 1 );
   }
   size = _msize( buffer );
   printf_s( "Size of block after realloc of 1000 more longs: %u\n",
            size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after malloc of 1000 longs: 4000
Size of block after realloc of 1000 more longs: 8000
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
