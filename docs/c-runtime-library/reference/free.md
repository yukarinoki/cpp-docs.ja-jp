---
title: 制限なし
ms.date: 4/2/2020
api_name:
- free
- _o_free
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
- free
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
ms.openlocfilehash: eefbe957ce5057b5038f98bc8da8fb2f0bdd3d1c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81345977"
---
# <a name="free"></a>制限なし

メモリ ブロックを割り当て解除または解放します。

## <a name="syntax"></a>構文

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
以前割り当てられ、解放されるメモリ ブロック。

## <a name="remarks"></a>解説

**free**関数は **、calloc**、 **malloc**、または**realloc**の呼び出しによって以前に割り当てられたメモリ ブロック (*memblock*) を割り当て解除します。 解放されたバイト数は、ブロックが割り当てられた (または再割り当てされた場合は**realloc)** ときに要求されたバイト数と同じです。 *memblock*が**NULL**の場合、ポインターは無視され **、free**はすぐに戻ります。 無効なポインタ **(calloc**、 **malloc**、または**realloc**によって割り当てられていないメモリブロックへのポインタ) を解放しようとすると、後続の割り当て要求に影響を与え、エラーが発生する可能性があります。

メモリの解放時にエラーが発生した場合は、エラーの性質上、オペレーティング システムからの情報が**errno**に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

アプリケーションが C ランタイム ライブラリのデバッグ バージョンにリンクされている場合、**自由**に[_free_dbg](free-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**free**は`__declspec(noalias)`マークが付いていますが、関数はグローバル変数を変更しないことが保証されています。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

[_malloca](malloca.md) を使用して割り当てられたメモリを解放するには、[_freea](freea.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|
|--------------|---------------------|
|**無料**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[malloc](malloc.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
