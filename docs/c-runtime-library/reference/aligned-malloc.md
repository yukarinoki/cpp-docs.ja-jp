---
title: _aligned_malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_malloc
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
- _aligned_malloc
- alligned_malloc
dev_langs:
- C++
helpviewer_keywords:
- aligned_malloc function
- _aligned_malloc function
ms.assetid: fb788d40-ee94-4039-aa4d-97d73dab1ca0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 656785fab5e5ffc8a6fa13711d2964f43cdc7d87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32393148"
---
# <a name="alignedmalloc"></a>_aligned_malloc

指定された配置の境界にメモリを割り当てます。

## <a name="syntax"></a>構文

```C
void * _aligned_malloc(
    size_t size,
    size_t alignment
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
要求されたメモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

## <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、操作に失敗しました。 ポインターがの倍数*配置*です。

## <a name="remarks"></a>コメント

**_aligned_malloc**に基づく[malloc](malloc.md)です。

**_aligned_malloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`、グローバル変数を変更せず、関数が保証されると、返されるポインターがエイリアス化されないを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

この関数は、設定**errno**に**ENOMEM**メモリの割り当てが失敗するか、要求されたサイズより大きい場合 **_HEAP_MAXREQ**です。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。 また、 **_aligned_malloc**パラメーターを検証します。 場合*配置*が 2 の累乗でないまたは*サイズ*ゼロ、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**NULL**設定と**errno**に**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_malloc**|\<malloc.h>|

## <a name="example"></a>例

```C
// crt_aligned_malloc.c

#include <malloc.h>
#include <stdio.h>

int main() {
    void    *ptr;
    size_t  alignment,
            off_set;

    // Note alignment should be 2^N where N is any positive int.
    alignment = 16;
    off_set = 5;

    // Using _aligned_malloc
    ptr = _aligned_malloc(100, alignment);
    if (ptr == NULL)
    {
        printf_s( "Error allocation aligned memory.");
        return -1;
    }
    if (((unsigned long long)ptr % alignment ) == 0)
        printf_s( "This pointer, %p, is aligned on %zu\n",
                  ptr, alignment);
    else
        printf_s( "This pointer, %p, is not aligned on %zu\n",
                  ptr, alignment);

    // Using _aligned_realloc
    ptr = _aligned_realloc(ptr, 200, alignment);
    if ( ((unsigned long long)ptr % alignment ) == 0)
        printf_s( "This pointer, %p, is aligned on %zu\n",
                  ptr, alignment);
    else
        printf_s( "This pointer, %p, is not aligned on %zu\n",
                  ptr, alignment);
    _aligned_free(ptr);

    // Using _aligned_offset_malloc
    ptr = _aligned_offset_malloc(200, alignment, off_set);
    if (ptr == NULL)
    {
        printf_s( "Error allocation aligned offset memory.");
        return -1;
    }
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",
                  ptr, off_set, alignment);
    else
        printf_s( "This pointer, %p, does not satisfy offset %zu "
                  "and alignment %zu\n",ptr, off_set, alignment);

    // Using _aligned_offset_realloc
    ptr = _aligned_offset_realloc(ptr, 200, alignment, off_set);
    if (ptr == NULL)
    {
        printf_s( "Error reallocation aligned offset memory.");
        return -1;
    }
    if ( ( (((unsigned long long)ptr) + off_set) % alignment ) == 0)
        printf_s( "This pointer, %p, is offset by %zu on alignment of %zu\n",
                  ptr, off_set, alignment);
    else
        printf_s( "This pointer, %p, does not satisfy offset %zu and "
                  "alignment %zu\n", ptr, off_set, alignment);

    // Note that _aligned_free works for both _aligned_malloc
    // and _aligned_offset_malloc. Using free is illegal.
    _aligned_free(ptr);
}
```

```Output
This pointer, 3280880, is aligned on 16
This pointer, 3280880, is aligned on 16
This pointer, 3280891, is offset by 5 on alignment of 16
This pointer, 3280891, is offset by 5 on alignment of 16
```

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
