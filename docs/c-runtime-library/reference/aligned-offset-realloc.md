---
title: _aligned_offset_realloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: d5f87f9bdfff262826b8d4cc4da86069588cf9db
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341458"
---
# <a name="alignedoffsetrealloc"></a>_aligned_offset_realloc

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更します。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_realloc(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
現在のメモリ ブロック ポインター。

*size*<br/>
メモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

**_aligned_offset_realloc**再割り当てされた (および移動) のメモリ ブロックに void ポインターを返します。 戻り値は**NULL** 、サイズが 0 のかどうか、およびバッファー引数ではありません**NULL**、または指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

**_aligned_offset_realloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`、グローバル変数を変更することがなく、関数が保証されると、返されるポインターがエイリアス化されないを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="remarks"></a>Remarks

ような[_aligned_offset_malloc](aligned-offset-malloc.md)、 **_aligned_offset_realloc**では構造内のオフセットに配置する構造。

**_aligned_offset_realloc**に基づいて**malloc**します。 使用しての詳細については **_aligned_offset_malloc**を参照してください[malloc](malloc.md)します。 場合 *_expand*は**NULL**、関数呼び出し **_aligned_offset_malloc**内部的にします。

この関数は、設定**errno**に**ENOMEM** 、メモリの割り当てに失敗した場合、または要求されたサイズより大きい場合 **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_offset_realloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*0 以外の場合、この関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
