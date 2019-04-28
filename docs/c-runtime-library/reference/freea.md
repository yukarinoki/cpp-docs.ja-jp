---
title: _freea
ms.date: 11/04/2016
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
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: ac9c5528755898b0de131bccf94185b501b0e720
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62333069"
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

*memblock*<br/>
以前割り当てられ、解放されるメモリ ブロック。

## <a name="return-value"></a>戻り値

なし。

## <a name="remarks"></a>Remarks

**_Freea**関数メモリ ブロックの割り当てを解除 (*_expand*) への呼び出しによって割り当てられていた[_malloca](malloca.md)します。 **_freea**ヒープまたはスタック上のメモリが割り当てられているかどうかにチェックします。 スタックに割り当てられた場合 **_freea**何も行われません。 ヒープ上で割り当てられている場合、解放されるバイト数は、ブロックが割り当てられたときに要求されたバイト数と同じです。 場合 *_expand*は**NULL**、ポインターは無視されますと **_freea**が直ちに返されます。 無効なポインターを解放しようとしています (によって割り当てられていないメモリ ブロックへのポインター **_malloca**) 以降の割り当て要求に影響を与えるし、エラーが発生する可能性があります。

**_freea**呼び出し**無料**ヒープにメモリが割り当てられることを検出した場合に内部的にします。 メモリが、ヒープまたはスタックのどちらにあるかは、割り当てられたメモリの直前のアドレスにメモリ内で配置されたマーカーによって決まります。

場合は、メモリの解放でエラーが発生した**errno**が障害の性質に関するオペレーティング システムからの情報を設定します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

呼び出し **_freea**に対するすべての呼び出しを伴う必要があります **_malloca**します。 呼び出すと、エラーも **_freea**同じメモリ上に 2 回クリックします。 特に、C ランタイム ライブラリのデバッグ バージョンと、アプリケーションがリンクしたとき[_malloc_dbg](malloc-dbg.md)機能を定義することで有効になっている **_CRTDBG_MAP_ALLOC**、不足しているを検索する方が簡単または呼び出しが重複して **_freea**します。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**_freea**がマークされている`__declspec(noalias)`、グローバル変数を変更することがなく、関数が保証されることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

## <a name="requirements"></a>必要条件

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
