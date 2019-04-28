---
title: _aligned_recalloc
ms.date: 11/04/2016
apiname:
- _aligned_recalloc
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
- aligned_recalloc
- _aligned_recalloc
helpviewer_keywords:
- aligned_recalloc function
- _aligned_recalloc function
ms.assetid: d3da3dcc-79ef-4273-8af5-ac7469420142
ms.openlocfilehash: ce505c5a389d4ff6aa12a88bfc47fb0a6f026eea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62335609"
---
# <a name="alignedrecalloc"></a>_aligned_recalloc

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更し、メモリを 0 に初期化します。

## <a name="syntax"></a>構文

```C
void * _aligned_recalloc(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
現在のメモリ ブロック ポインター。

*number*<br/>
要素の数。

*size*<br/>
各要素のサイズ (バイト単位)。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

## <a name="return-value"></a>戻り値

**_aligned_recalloc**再割り当てされた (および移動) のメモリ ブロックに void ポインターを返します。 戻り値は**NULL** 、サイズが 0 のかどうか、およびバッファー引数ではありません**NULL**、または指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

メモリを再割り当てしてブロックのアラインメントを変更すると、エラーになります。

## <a name="remarks"></a>Remarks

**_aligned_recalloc**に基づいて**malloc**します。 使用しての詳細については **_aligned_offset_malloc**を参照してください[malloc](malloc.md)します。

この関数は、設定**errno**に**ENOMEM** 、メモリの割り当てに失敗した場合、または要求されたサイズより大きい場合 **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_recalloc**パラメーターを検証します。 場合*配置*が累乗でない」の説明に従って 2 に、この関数が、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_recalloc**|\<malloc.h>|

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
[_recalloc](recalloc.md)<br/>
[_aligned_offset_recalloc](aligned-offset-recalloc.md)<br/>
