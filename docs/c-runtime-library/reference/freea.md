---
title: _freea | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _freea
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
apitype: DLLExport
f1_keywords:
- freea
- _freea
dev_langs:
- C++
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8ac01f965e159dae19bbbd748c1692058063a211
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32403604"
---
# <a name="freea"></a>_freea

メモリ ブロックを割り当て解除または解放します。

## <a name="syntax"></a>構文

```C
void _freea(
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*_expand*<br/>
以前割り当てられ、解放されるメモリ ブロック。

## <a name="return-value"></a>戻り値

なし。

## <a name="remarks"></a>コメント

**_Freea**関数にメモリ ブロックの割り当てを解除 (*_expand*) への呼び出しによって割り当てられていた[_malloca](malloca.md)です。 **_freea**ヒープまたはスタックにメモリが割り当てられたかどうかかどうかを確認します。 場合は、スタックに割り当てられた **_freea**何も行われません。 ヒープ上で割り当てられている場合、解放されるバイト数は、ブロックが割り当てられたときに要求されたバイト数と同じです。 場合 *_expand*は**NULL**、ポインターは無視されますと **_freea**が直ちに返されます。 無効なポインターを解放しようとしています (によって割り当てられていないメモリ ブロックへのポインター **_malloca**) 以降の割り当て要求には影響し、エラーが発生する可能性があります。

**_freea**呼び出し**空き**ヒープにメモリが割り当てられていることを検出した場合に内部的にします。 メモリが、ヒープまたはスタックのどちらにあるかは、割り当てられたメモリの直前のアドレスにメモリ内で配置されたマーカーによって決まります。

場合は、メモリの解放でエラーが発生した**errno**エラーの性質に関するオペレーティング システムからの情報に設定します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

呼び出し **_freea**すべての呼び出しを伴う必要があります **_malloca**です。 呼び出すと、エラーも **_freea**は同じメモリに 2 回クリックします。 特に、C ランタイム ライブラリのデバッグ バージョンと、アプリケーションがリンクしたとき[_malloc_dbg](malloc-dbg.md)機能を定義することで有効に **_CRTDBG_MAP_ALLOC**、不足している検索する方が簡単か呼び出しが重複して **_freea**です。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

**_freea**がマークされている`__declspec(noalias)`関数がグローバル変数を変更せず保証されることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

## <a name="requirements"></a>要件

|関数|必須ヘッダー|
|--------------|---------------------|
|**_freea**|\<stdlib.h> と \<malloc.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_malloca](malloca.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[メモリ割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
