---
title: _aligned_offset_recalloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_recalloc
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
- aligned_offset_recalloc
- _aligned_offset_recalloc
helpviewer_keywords:
- aligned_offset_recalloc function
- _aligned_offset_recalloc function
ms.assetid: a258f54e-eeb4-4853-96fc-007d710f98e9
ms.openlocfilehash: 5ee163d257665b5481d6ab1ead54698ace1ef210
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50561994"
---
# <a name="alignedoffsetrecalloc"></a>_aligned_offset_recalloc

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更し、メモリを 0 に初期化します。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
現在のメモリ ブロック ポインター。

*数*<br/>
要素の数。

*size*<br/>
各要素の長さ (バイト単位)。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

**_aligned_offset_recalloc**再割り当てされた (および移動) のメモリ ブロックに void ポインターを返します。 戻り値は**NULL** 、サイズが 0 のかどうか、およびバッファー引数ではありません**NULL**、または指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

**_aligned_offset_recalloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`、グローバル変数を変更することがなく、関数が保証されると、返されるポインターがエイリアス化されないを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="remarks"></a>Remarks

ような[_aligned_offset_malloc](aligned-offset-malloc.md)、 **_aligned_offset_recalloc**では構造内のオフセットに配置する構造。

**_aligned_offset_recalloc**に基づいて**malloc**します。 使用しての詳細については **_aligned_offset_malloc**を参照してください[malloc](malloc.md)します。 場合 *_expand*は**NULL**、関数呼び出し **_aligned_offset_malloc**内部的にします。

この関数は、設定**errno**に**ENOMEM**場合や、メモリの割り当てに失敗した場合、要求されたサイズ (*数* * *サイズ*) よりも大きかった **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_offset_recalloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*が要求されたサイズに等しいと 0 以外の場合より大きい」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_recalloc**|\<malloc.h>|

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_recalloc](aligned-recalloc.md)<br/>
