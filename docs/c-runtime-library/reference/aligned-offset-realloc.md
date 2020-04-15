---
title: _aligned_offset_realloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_realloc
- _o__aligned_offset_realloc
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
- aligned_offset_realloc
- _aligned_offset_realloc
helpviewer_keywords:
- aligned_offset_realloc function
- _aligned_offset_realloc function
ms.assetid: e0263533-991e-41b0-acc9-1b8a51ab9ecd
ms.openlocfilehash: b27f5000a48ec3aafe37c6bd59e9b9acddd5bec5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350572"
---
# <a name="_aligned_offset_realloc"></a>_aligned_offset_realloc

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

*サイズ*<br/>
メモリ割り当てのサイズ。

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*offset*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

**_aligned_offset_realloc**は、再割り当てされた (そして移動される可能性のある) メモリ ブロックへの void ポインタを返します。 サイズが 0 で、buffer 引数が**NULL**でない場合、またはブロックを指定されたサイズに拡張するのに十分なメモリがない場合は、戻り値は**NULL**です。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

**_aligned_offset_realloc**マークが`__declspec(noalias)`付`__declspec(restrict)`き、 とは、関数がグローバル変数を変更しないことが保証されており、返されるポインターが別名として使用されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

## <a name="remarks"></a>解説

[_aligned_offset_malloc](aligned-offset-malloc.md)と同様**に、_aligned_offset_realloc**構造を構造体内のオフセットに配置できます。

**_aligned_offset_realloc**は**malloc**に基づいています。 **_aligned_offset_malloc**の使用方法の詳細については、「 [malloc](malloc.md)」を参照してください。 *memblock*が**NULL**の場合、関数は内部的**に_aligned_offset_malloc**呼び出します。

この関数は、メモリ割り当てが失敗した場合、または要求されたサイズが _HEAP_MAXREQ より大きい場合に**errno**を**ENOMEM** **に**設定します。 **errno**の詳細については、「 [errno 、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また **、_aligned_offset_realloc**はパラメータを検証します。 *アライメント*が 2 の累乗でない場合、または*offset*が*size*および 0 以外の値以上の場合、この関数は無効なパラメーター ハンドラーを呼び[出します](../../c-runtime-library/parameter-validation.md)。 実行を続行できる場合、この関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_realloc**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの配置](../../c-runtime-library/data-alignment.md)<br/>
