---
title: _recalloc
ms.date: 4/2/2020
api_name:
- _recalloc
- _o__recalloc
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
- _recalloc
- recalloc
helpviewer_keywords:
- _recalloc function
- recalloc function
ms.assetid: 1db8305a-3f03-418c-8844-bf9149f63046
ms.openlocfilehash: 57972a48336d8dd362b5da7513c854703134921b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338120"
---
# <a name="_recalloc"></a>_recalloc

**リアルロック**と**カロック**の組み合わせ。 メモリ内の配列を再割り当てし、その要素を 0 に初期化します。

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
以前に割り当てられていたメモリ ブロックへのポインター。

*数*<br/>
要素の数。

*サイズ*<br/>
各要素の長さ (バイト単位)。

## <a name="return-value"></a>戻り値

**_recalloc**は、再割り当てされた (そして移動される可能性のある) メモリ ブロックへの**void**ポインタを返します。

ブロックを指定されたサイズに拡張するのに十分なメモリがない場合、元のブロックは変更されず **、NULL**が返されます。

要求されたサイズがゼロの場合 *、memblock*が指すブロックは解放されます。戻り値は**NULL**で *、memblock*は解放されたブロックを指し示しています。

戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには **、** 戻り値にキャストする型を使用します。

## <a name="remarks"></a>解説

**_recalloc**関数は、割り当てられたメモリ ブロックのサイズを変更します。 *memblock*引数は、メモリ ブロックの先頭を指します。 *memblock*が**NULL**の場合 **、_recalloc**は[calloc](calloc.md)と同じように動作し、*新しい番号* * *サイズ*バイトのブロックを割り当てます。 各要素は 0 で初期化されます。 *memblock*が**NULL**でない場合は **、calloc**、 [malloc](malloc.md)、または[realloc](realloc.md)に対する以前の呼び出しによって返されるポインターでなければなりません。

新しいブロックは新しいメモリ位置に置くことができるため **、_recalloc**によって返されるポインターが*memblock*引数を通じて渡されるポインターであるとは限りません。

**_recalloc**は、メモリ割り当てが失敗した場合、または要求されたメモリの量が_HEAP_MAXREQを超えた場合に **、errno**を**ENOMEM** **に**設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

**recalloc は**、新しいハンドラ モードを設定するために C++ [_set_new_mode](set-new-mode.md)関数を使用するために**realloc**を呼び出します。 新しいハンドラモードは、障害発生時に**realloc**[、realloc](set-new-handler.md)が_set_new_handlerで設定された新しいハンドラルーチンを呼び出すかどうかを示します。 デフォルトでは **、realloc**はメモリの割り当てに失敗した場合に新しいハンドラルーチンを呼び出しません。 このデフォルトの動作をオーバーライドして **、_recallocが**メモリの割り当てに失敗した場合に **、realloc**は、new 演算子が同じ理由で失敗した場合と同じ方法で**新しい**ハンドラー ルーチンを呼び出すことができます。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

この呼び出しはプログラムの最初の方で指定するか、NEWMODE.OBJ にリンクします。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされている場合 **、_recalloc**[は _recalloc_dbg](recalloc-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**_recalloc**マークが`__declspec(noalias)`付`__declspec(restrict)`き、 と は、関数がグローバル変数を変更しないことが保証され、返されるポインターが別名として指定されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_recalloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_recalloc_dbg](recalloc-dbg.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
[無料](free.md)<br/>
[リンク オプション](../../c-runtime-library/link-options.md)<br/>
