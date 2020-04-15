---
title: realloc
ms.date: 4/2/2020
api_name:
- realloc
- _o_realloc
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
- api-ms-win-crt-heap-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _brealloc
- _nrealloc
- realloc
- _frealloc
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
ms.openlocfilehash: 964c465a95d44de9d8a4d399f23ec43f8a3a6692
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81332927"
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

*memblock*<br/>
以前に割り当てられていたメモリ ブロックへのポインター。

*サイズ*<br/>
新しいサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

**realloc は**、再割り当てされた (そしておそらく移動した) メモリ ブロックへの**void**ポインタを返します。

ブロックを指定されたサイズに拡張するのに十分なメモリがない場合、元のブロックは変更されず **、NULL**が返されます。

*size*が 0 の場合 *、memblock*が指すブロックは解放されます。戻り値は**NULL**で *、memblock*は解放されたブロックを指し示しています。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには **、** 戻り値にキャストする型を使用します。

## <a name="remarks"></a>解説

**realloc**関数は、割り当てられたメモリ ブロックのサイズを変更します。 *memblock*引数は、メモリ ブロックの先頭を指します。 *memblock*が**NULL**の場合 **、realloc**は**malloc**と同じように動作し、*サイズ・* バイトの新しいブロックを割り当てます。 *memblock*が**NULL**でない場合は **、calloc**、 **malloc**、または**realloc**に対する以前の呼び出しによって返されるポインターでなければなりません。

*size*引数は、ブロックの新しいサイズをバイト単位で指定します。 新旧のサイズのうち、小さい方のブロックの内容は変更されませんが、新しいブロックの場所は異なる場合があります。 新しいブロックは新しいメモリ位置に置くことができるので **、realloc**によって返されるポインタが*memblock*引数を通って渡されるポインタであるとは限りません。 **realloc**は、バッファーの増加の場合に新しく割り当てられたメモリをゼロにしません。

**realloc は**、メモリ割り当てが失敗した場合、または要求されたメモリの量が _HEAP_MAXREQ を超えた場合に **、errno**を**ENOMEM** **に**設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**realloc は**、新しいハンドラー モードを設定する C++ [_set_new_mode](set-new-mode.md)関数を使用するために**malloc**を呼び出します。 新しいハンドラ モードは、失敗時に**malloc**が[_set_new_handler](set-new-handler.md)で設定された新しいハンドラ ルーチンを呼び出すかどうかを示します。 既定では **、malloc**はメモリの割り当てに失敗した場合に新しいハンドラー ルーチンを呼び出しません。 **realloc**がメモリの割り当てに失敗した場合 **、malloc**は、同じ理由で失敗した場合と同じように**新しい**ハンドラー ルーチンを呼び出すので、この既定の動作をオーバーライドできます。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされると **、realloc**は[_realloc_dbg](realloc-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**realloc**は`__declspec(noalias)`マーク`__declspec(restrict)`され、 関数がグローバル変数を変更しないことが保証され、返されるポインターが別名化されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**realloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[無料](free.md)<br/>
[malloc](malloc.md)<br/>
