---
title: calloc
description: C ランタイムライブラリ関数 calloc は、ゼロ初期化されたメモリを割り当てます。
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 067ce6f347f4b24ad8c85990e70fe4d79305535c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213633"
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

*number*<br/>
要素の数。

*size*<br/>
各要素の長さ (バイト単位)。

## <a name="return-value"></a>戻り値

**calloc**は、割り当てられた領域へのポインターを返します。 戻り値で指し示される記憶域は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されます。 以外の型へのポインターを取得するには **`void`** 、戻り値に型キャストを使用します。

## <a name="remarks"></a>解説

**Calloc**関数は、長さ*サイズ*のバイトごとに、*数値*要素の配列にストレージ領域を割り当てます。 各要素は 0 で初期化されます。

**calloc**は、メモリ割り当てが失敗した場合、または要求されたメモリの量が **_HEAP_MAXREQ**を超えた場合に、 **errno**を**ENOMEM**に設定します。 その他のエラー コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

Microsoft の実装では、 *number*または*size*が0の場合、 **calloc**は0以外のサイズの割り当てられたブロックへのポインターを返します。 返されたポインターに対して読み取りまたは書き込みを行おうとすると、未定義の動作が発生します。

**calloc**は、C++ [_set_new_mode](set-new-mode.md)関数を使用して*新しいハンドラーモード*を設定します。 新しいハンドラーモードは、エラー発生時に、 [_set_new_handler](set-new-handler.md)によって**設定され**た新しいハンドラールーチンを呼び出すかどうかを示します。 既定では、 **calloc**は、メモリの割り当てに失敗したときに新しいハンドラールーチンを呼び出しません。 **Calloc**がメモリの割り当てに失敗したときに、同じ理由で失敗した場合と同じ方法で新しいハンドラールーチンを呼び出すように、この既定の動作をオーバーライドできます **`new`** 。 既定の動作をオーバーライドするには、次の関数を呼び出します。

```C
_set_new_mode(1);
```

プログラムの初期状態で作成するか、Newmode を使用してリンク*します。OBJ* (「[リンクオプション](../../c-runtime-library/link-options.md)」を参照)。

アプリケーションが C ランタイムライブラリのデバッグバージョンにリンクされている場合、 **calloc**は[_calloc_dbg](calloc-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**calloc**はとマークされてい `__declspec(noalias)` `__declspec(restrict)` ます。つまり、関数はグローバル変数を変更せず、返されるポインターにエイリアスが設定されていないことが保証されます。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**calloc**|\<stdlib.h> および \<malloc.h>|

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

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[空け](free.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
