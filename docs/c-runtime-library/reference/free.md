---
title: free | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- free
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
- free
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- free function
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: fc6dfd832d18dbabc1ebc10aec252cc8afe15346
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32402518"
---
# <a name="free"></a>free

メモリ ブロックを割り当て解除または解放します。

## <a name="syntax"></a>構文

```C
void free(
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*_expand*以前に割り当てられたメモリ ブロックは解放されません。

## <a name="remarks"></a>コメント

**空き**関数にメモリ ブロックの割り当てを解除 (*_expand*) への呼び出しによって割り当てられていた**calloc**、 **malloc**、または**realloc**です。 解放されたバイト数が、要求されたバイト数、ブロックが割り当てられたときと同じ (またはの場合、再割り当てされた**realloc**)。 場合 *_expand*は**NULL**、ポインターは無視されますと**空き**が直ちに返されます。 無効なポインターを解放しようとしています (によって割り当てられていないメモリ ブロックへのポインター **calloc**、 **malloc**、または**realloc**) 以降の割り当て要求に影響を与える可能性がありますエラーが発生します。

場合は、メモリの解放でエラーが発生した**errno**エラーの性質に関するオペレーティング システムからの情報に設定します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

C ランタイム ライブラリのデバッグ バージョンとリンクするアプリケーション**空き**に解決される[_free_dbg](free-dbg.md)です。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

**空き**がマークされている`__declspec(noalias)`関数がグローバル変数を変更せず保証されることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

[_malloca](malloca.md) を使用して割り当てられたメモリを解放するには、[_freea](freea.md) を使用します。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**free**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

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
