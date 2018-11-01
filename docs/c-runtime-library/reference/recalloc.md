---
title: _recalloc
ms.date: 11/04/2016
apiname:
- _recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 3bcc238dcb950a8e30af16efc557e99d933efe92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436518"
---
# <a name="recalloc"></a>_recalloc

組み合わせた**realloc**と**calloc**します。 メモリ内の配列を再割り当てし、その要素を 0 に初期化します。

## <a name="syntax"></a>構文

```C
void *_recalloc(
   void *memblock
   size_t num,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
以前に割り当てられたメモリ ブロックへのポインター。

*数*<br/>
要素の数。

*size*<br/>
各要素の長さ (バイト単位)。

## <a name="return-value"></a>戻り値

**_recalloc**を返します、 **void**再割り当てされた (および移動) のメモリ ブロックへのポインター。

指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合、元のブロックは変更されず、および**NULL**が返されます。

かどうか、要求されたサイズが 0 の場合は、によって示されるブロック*別*が解放されます。 戻り値は**NULL**、と*別*解放されたブロックをポイントしたままです。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 以外の型へのポインターを取得する**void**型、戻り値のキャストを使用します。

## <a name="remarks"></a>Remarks

**_Recalloc**関数、割り当てられたメモリ ブロックのサイズを変更します。 *_Expand*引数はメモリ ブロックの先頭を指します。 場合 *_expand*は**NULL**、 **_recalloc**と同様に動作[calloc](calloc.md)し、新しいブロックを割り当てます*数* * *サイズ*バイト。 各要素は 0 に初期化されます。 場合 *_expand*ない**NULL**、以前の呼び出しによって返されたポインターである必要があります**calloc**、 [malloc](malloc.md)、または[realloc](realloc.md).

ポインターがによって返されるため、新しいブロックは、新しいメモリ位置に配置できる、 **_recalloc**を通じて渡されたポインターにするとは限りません、 *_expand*引数。

**_recalloc**設定**errno**に**ENOMEM** 、メモリの割り当てが失敗した場合、または、要求されたメモリ量を超える場合 **_HEAP_MAXREQ**します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**recalloc**呼び出し**realloc** 、C++ を使用するには[_set_new_mode](set-new-mode.md)新しいハンドラー モードを設定します。 新しいハンドラー モードを示すかどうか、失敗した場合、 **realloc**によって設定された新しいハンドラー ルーチンを呼び出すには、 [_set_new_handler](set-new-handler.md)します。 既定では、 **realloc**でメモリの割り当ての失敗によって新しいハンドラー ルーチンを呼び出しません。 この既定の動作をオーバーライドするように、 **_recalloc** 、メモリの割り当てに失敗した**realloc**に同じ新しいハンドラー ルーチンを呼び出す方法、**新しい**演算子同じ理由で失敗した場合は。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします。

アプリケーションが、C ランタイム ライブラリのデバッグ バージョンにリンクされている場合 **_recalloc**に解決される[_recalloc_dbg](recalloc-dbg.md)します。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**_recalloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`関数は、グローバル変数を変更しないように保証し、返されるポインターがエイリアス化されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[free](free.md)<br/>
[リンク オプション](../../c-runtime-library/link-options.md)<br/>
