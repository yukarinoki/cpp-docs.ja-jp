---
title: calloc
ms.date: 11/04/2016
apiname:
- calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: 59aa535136cf32ea5dd68b8917ec969eee41e2ae
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666974"
---
# <a name="calloc"></a>calloc

要素を 0 に初期化した配列のメモリを割り当てます。

## <a name="syntax"></a>構文

```C
void *calloc(
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*数*<br/>
要素の数。

*size*<br/>
各要素の長さ (バイト単位)。

## <a name="return-value"></a>戻り値

**calloc**割り当てた領域へのポインターを返します。 戻り値で指し示される記憶域は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されます。 以外の型へのポインターを取得する**void**型、戻り値のキャストを使用します。

## <a name="remarks"></a>Remarks

**Calloc**関数の配列の記憶域を割り当てます*数*長さの各要素は、*サイズ*バイト。 各要素は 0 に初期化されます。

**calloc**設定**errno**に**ENOMEM**メモリ割り当てが失敗した場合、または、要求されたメモリ量を超える場合 **_HEAP_MAXREQ**します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**calloc**呼び出し**malloc** 、C を使用して[_set_new_mode](set-new-mode.md)新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **malloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)します。 既定では、 **malloc**でメモリの割り当ての失敗によって新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドするように、 **calloc** 、メモリの割り当てに失敗した**malloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子が同じ理由で失敗しました。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします (「[リンク オプション](../../c-runtime-library/link-options.md)」を参照してください)。

アプリケーションが、C ランタイム ライブラリのデバッグ バージョンにリンクされている場合**calloc**に解決される[_calloc_dbg](calloc-dbg.md)します。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**calloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`関数は、グローバル変数を変更しないように保証し、返されるポインターがエイリアス化されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**calloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_calloc.c
// This program uses calloc to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>

int main( void )
{
   long *buffer;

   buffer = (long *)calloc( 40, sizeof( long ) );
   if( buffer != NULL )
      printf( "Allocated 40 long integers\n" );
   else
      printf( "Can't allocate memory\n" );
   free( buffer );
}
```

```Output
Allocated 40 long integers
```

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[free](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
