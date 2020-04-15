---
title: _aligned_offset_malloc
ms.date: 4/2/2020
api_name:
- _aligned_offset_malloc
- _o__aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 1f13afbab75d2926d1c642c1430a3ffe5ecbac8d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350585"
---
# <a name="_aligned_offset_malloc"></a>_aligned_offset_malloc

指定された配置の境界にメモリを割り当てます。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_malloc(
   size_t size,
   size_t alignment,
   size_t offset
);
```

### <a name="parameters"></a>パラメーター

*サイズ*<br/>
要求されたメモリ割り当てのサイズ。

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*offset*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへの**ポインター。**

## <a name="remarks"></a>解説

**_aligned_offset_malloc**は、入れ子になった要素に対して配置が必要な場合に便利です。たとえば、入れ子になったクラスで配置が必要な場合です。

**_aligned_offset_malloc**は**malloc**に基づいています。詳細については、「 [malloc](malloc.md)」を参照してください。

**_aligned_offset_malloc**マークが`__declspec(noalias)`付`__declspec(restrict)`き、 と は、関数がグローバル変数を変更しないことが保証されており、返されたポインターが別名として指定されないことを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

この関数は、メモリ割り当てが失敗した場合、または要求されたサイズが _HEAP_MAXREQ より大きい場合に**errno**を**ENOMEM** **に**設定します。 **errno**の詳細については、「 [errno 、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また **、_aligned_offset_malloc**はパラメータを検証します。 *アライメント*が 2 の累乗でない場合、または*offset*が*size*および 0 以外の値以上の場合、この関数は無効なパラメーター ハンドラーを呼び[出します](../../c-runtime-library/parameter-validation.md)。 実行を続行できる場合、この関数は**NULL を**返し **、errno**を**EINVAL**に設定します。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの配置](../../c-runtime-library/data-alignment.md)<br/>
