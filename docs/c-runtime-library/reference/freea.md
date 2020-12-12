---
description: '詳細については、次を参照してください: _freea'
title: _freea
ms.date: 11/04/2016
api_name:
- _freea
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- freea
- _freea
helpviewer_keywords:
- _freea function
- freea function
- memory deallocation
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
ms.openlocfilehash: 6d6f57117265e62e7d3c822110b52f69cb65ffac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97282966"
---
# <a name="_freea"></a>_freea

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

[なし] :

## <a name="remarks"></a>解説

**_Freea** 関数は、以前に [_malloca](malloca.md)の呼び出しによって割り当てられたメモリブロック (*memblock*) を解放します。 **_freea** は、メモリがヒープまたはスタックに割り当てられたかどうかを確認します。 スタックに割り当てられている場合、 **_freea** は何も行いません。 ヒープ上で割り当てられている場合、解放されるバイト数は、ブロックが割り当てられたときに要求されたバイト数と同じです。 *Memblock* が **NULL** の場合、ポインターは無視され、 **_freea** 直ちに制御が戻ります。 無効なポインター ( **_malloca** によって割り当てられていないメモリブロックへのポインター) を解放しようとすると、後続の割り当て要求に影響し、エラーが発生する可能性があります。

メモリがヒープに割り当てられていることが判明した場合、 **_freea** は内部的に **解放** されます。 メモリが、ヒープまたはスタックのどちらにあるかは、割り当てられたメモリの直前のアドレスにメモリ内で配置されたマーカーによって決まります。

メモリの解放中にエラーが発生した場合、エラーの性質上、オペレーティングシステムからの情報が **errno** に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

メモリ ブロックを解放すると、[_heapmin](heapmin.md) が、未使用の領域を結合して、それらをオペレーティング システムに戻すことで、ヒープ上の空きメモリの量を最小限に抑えます。 オペレーティング システムにリリースされない解放されたメモリは、空きプールに復元され、再度割り当てに使用できます。

**_Freea** の呼び出しは、 **_malloca** へのすべての呼び出しに付随している必要があります。 同じメモリで2回 **_freea** を呼び出すこともできません。 アプリケーションが C ランタイムライブラリのデバッグバージョンに関連付けられている場合 (特に、 **_CRTDBG_MAP_ALLOC** を定義することによって有効にされた [_malloc_dbg](malloc-dbg.md)機能の場合)、不足している **_freea** または重複している呼び出しを簡単に見つけることができます。 デバッグ プロセス中のヒープの管理方法の詳細については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

**_freea** はとマークされてい `__declspec(noalias)` ます。つまり、関数はグローバル変数を変更しないことが保証されます。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

## <a name="requirements"></a>要件

|機能|必須ヘッダー|
|--------------|---------------------|
|**_freea**|\<stdlib.h> および \<malloc.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

「[_malloca](malloca.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[メモリの割り当て](../../c-runtime-library/memory-allocation.md)<br/>
[_malloca](malloca.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[realloc](realloc.md)<br/>
[_free_dbg](free-dbg.md)<br/>
[_heapmin](heapmin.md)<br/>
