---
title: _aligned_offset_malloc
ms.date: 11/04/2016
apiname:
- _aligned_offset_malloc
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
- _aligned_offset_malloc
- aligned_offset_malloc
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
ms.openlocfilehash: 824edfd8bb96d805a030fb205dee62fa9eb4fd06
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644640"
---
# <a name="alignedoffsetmalloc"></a>_aligned_offset_malloc

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

*size*<br/>
要求されたメモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

## <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、操作に失敗しました。

## <a name="remarks"></a>Remarks

**_aligned_offset_malloc** ; 入れ子になった要素の配置が必要な場合に便利ですたとえば、入れ子になったクラスに対するアラインメントが必要です。

**_aligned_offset_malloc**に基づいて**malloc**; 詳細についてを参照してください[malloc](malloc.md)します。

**_aligned_offset_malloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`、グローバル変数を変更することがなく、関数が保証されると、返されるポインターがエイリアス化されないを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

この関数は、設定**errno**に**ENOMEM** 、メモリの割り当てに失敗した場合、または要求されたサイズより大きい場合 **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_offset_malloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*0 以外の場合、この関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
