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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 0e0a53dd9d24634442c8dd456e4f9d38f742e292
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82920423"
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

**Free**関数は、以前に**calloc**、 **malloc**、または**realloc**への呼び出しによって割り当てられたメモリブロック (*memblock*) を解放します。 解放されたバイト数は、ブロックが割り当てられた (または再**割り当ての場合**は再割り当てされた) ときに要求されたバイト数と同じです。 *Memblock*が**NULL**の場合、ポインターは無視され、すぐに**解放**されます。 無効なポインター ( **calloc**、 **malloc**、または**realloc**によって割り当てられていないメモリブロックへのポインター) を解放しようとすると、後続の割り当て要求に影響し、エラーが発生する可能性があります。

メモリの解放中にエラーが発生した場合、エラーの性質上、オペレーティングシステムからの情報が**errno**に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

アプリケーションが C ランタイムライブラリのデバッグバージョンにリンクされている場合、 **free**は[_free_dbg](free-dbg.md)に解決されます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**free**はと`__declspec(noalias)`マークされています。これは、関数がグローバル変数を変更しないことが保証されることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

[_malloca](malloca.md) を使用して割り当てられたメモリを解放するには、[_freea](freea.md) を使用します。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|
|--------------|---------------------|
|**空け**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[malloc](malloc.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_alloca](alloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
[_freea](freea.md)<br/>
