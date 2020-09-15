---
title: realloc
description: Realloc (); の API リファレンスメモリブロックを再割り当てします。
ms.date: 9/11/2020
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: c68909b2f5d73959465d63af522ceeb00c8ce23e
ms.sourcegitcommit: b492516cc65120250b9ea23f96f7f63f37f99fae
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/14/2020
ms.locfileid: "90075817"
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

*`memblock`*\
以前に割り当てられていたメモリ ブロックへのポインター。

*`size`*\
新しいサイズ (バイト単位)。

## <a name="return-value"></a>戻り値

**`realloc`** 再 **`void`** 割り当てされた (移動された可能性もある) メモリブロックへのポインターを返します。

指定されたサイズまでブロックを拡張するのに十分なメモリが不足している場合、元のブロックは変更されずに残り、 **`NULL`** が返されます。

*`size`* が0の場合、が指すブロックは *`memblock`* 解放されます。戻り値は **`NULL`** で、 *`memblock`* は解放されたブロックを指します。

戻り値は、任意の種類のオブジェクトを格納するために適切にアラインされた記憶域スペースを指します。 以外の型へのポインターを取得するには **`void`** 、戻り値に型キャストを使用します。

## <a name="remarks"></a>解説

> [!NOTE]
> **`realloc`** は、新しい動作が Windows オペレーティングシステムと互換性がないため、C17 動作を実装するために更新されていません。

関数は、 **`realloc`** 割り当てられたメモリブロックのサイズを変更します。 引数は、 *`memblock`* メモリブロックの先頭を指します。 がの場合 *`memblock`* **`NULL`** 、は **`realloc`** と同じように動作し、 **`malloc`** 新しいバイトのブロックを割り当て *`size`* ます。 がでない場合は、、 *`memblock`* **`NULL`** 、またはの前回の呼び出しによって返されたポインターである必要があり **`calloc`** **`malloc`** **`realloc`** ます。

引数は、 *`size`* ブロックの新しいサイズをバイト単位で示します。 新旧のサイズのうち、小さい方のブロックの内容は変更されませんが、新しいブロックの場所は異なる場合があります。 新しいブロックは新しいメモリ位置にある可能性があるため、によって返されるポインターは、 **`realloc`** 引数を通じて渡されるポインターであるとは限りません *`memblock`* 。 **`realloc`** では、バッファーのサイズが増加した場合、新しく割り当てられたメモリはゼロになりません。

**`realloc`****`errno`** **`ENOMEM`** メモリ割り当てが失敗した場合、または要求されたメモリの量がを超えた場合に、をに設定し **`_HEAP_MAXREQ`** ます。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**`realloc`****`malloc`** は、C++ の[_set_new_mode](set-new-mode.md)関数を使用して新しいハンドラーモードを設定するためにを呼び出します。 新しいハンドラーモードは、エラーが発生した **`malloc`** ときに [_set_new_handler](set-new-handler.md)によって設定された新しいハンドラールーチンを呼び出すかどうかを示します。 既定で **`malloc`** は、は、メモリの割り当てに失敗したときに新しいハンドラールーチンを呼び出しません。 この既定の動作をオーバーライドすると、がメモリの割り当てに失敗したときに、 **`realloc`** **`malloc`** 同じ理由で失敗した場合と同じ方法で新しいハンドラールーチンを呼び出すことができ **`new`** ます。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

アプリケーションが C ランタイムライブラリのデバッグバージョンにリンクされている場合、は _realloc_dbg として解決され **`realloc`** ます。 [_realloc_dbg](realloc-dbg.md) デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**`realloc`** はとマークされてい `__declspec(noalias)` `__declspec(restrict)` ます。つまり、関数はグローバル変数を変更せず、返されるポインターがエイリアス化されていないことが保証されます。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**`realloc`**|\<stdlib.h> および \<malloc.h>|

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

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)\
[calloc](calloc.md)\
[空け](free.md)\
[malloc](malloc.md)
