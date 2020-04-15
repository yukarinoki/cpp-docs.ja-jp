---
title: calloc
description: C ランタイム ライブラリ関数 calloc は、ゼロ初期化メモリを割り当てます。
ms.date: 4/2/2020
api_name:
- calloc
- _o_calloc
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
- calloc
helpviewer_keywords:
- memory allocation, arrays
- calloc function
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
ms.openlocfilehash: fb4f7d6dc059023d34cb0b811edf5dfb48cb7a34
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81333652"
---
# <a name="calloc"></a>calloc

要素を 0 に初期化した配列のメモリを割り当てます。

## <a name="syntax"></a>構文

```C
void *calloc(
   size_t number,
   size_t size
);
```

### <a name="parameters"></a>パラメーター

*数*<br/>
要素の数。

*サイズ*<br/>
各要素の長さ (バイト単位)。

## <a name="return-value"></a>戻り値

**calloc**は、割り当てられたスペースへのポインターを戻します。 戻り値で指し示される記憶域は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されます。 void 以外の型へのポインターを取得するには **、** 戻り値にキャストする型を使用します。

## <a name="remarks"></a>解説

**calloc**関数は、長*さサイズ*のバイトのそれぞれ、*数値*要素の配列の記憶領域を割り当てます。 各要素は 0 で初期化されます。

**calloc は**、メモリ割り当てが失敗した場合、または要求されたメモリの量が _HEAP_MAXREQ を超えた場合に **、errno**を**ENOMEM** **に**設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

Microsoft の実装では、*数値*または*サイズ*が 0 の場合 **、calloc**は割り当てられた 0 以外のサイズのブロックへのポインターを返します。 返されたポインターを読み取りまたは書き込みしようとすると、未定義の動作が発生します。

**calloc**は C++ [_set_new_mode](set-new-mode.md)関数を使用して *、新しいハンドラ モード*を設定します。 新しいハンドラ モードは、失敗した場合に **、calloc**が[_set_new_handler](set-new-handler.md)で設定された新しいハンドラ ルーチンを呼び出すかどうかを示します。 デフォルトでは **、calloc**はメモリの割り当てに失敗した場合に新しいハンドラルーチンを呼び出しません。 **calloc**がメモリの割り当てに失敗した場合に、同じ理由で失敗した場合と同じ方法で**new**ハンドラー ルーチンを呼び出す場合、この既定の動作をオーバーライドできます。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

プログラムの早い段階で、または NEWMODE とリンク*します。OBJ* ([リンクオプション](../../c-runtime-library/link-options.md)を参照)。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされると **、calloc**は[_calloc_dbg](calloc-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**calloc**は`__declspec(noalias)`マーク`__declspec(restrict)`され、 関数がグローバル変数を変更しないことが保証され、返されるポインターがエイリアス化されていないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**calloc**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
[無料](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
