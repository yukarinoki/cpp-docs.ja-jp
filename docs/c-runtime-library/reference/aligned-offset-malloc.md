---
title: _aligned_offset_malloc | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc function
- aligned_offset_malloc function
ms.assetid: 447681a3-7c95-4655-86ba-fa3a4ca4c521
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8bcc5fe0d786c7fdb04455f231cc3c8e60b53a22
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32392846"
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

## <a name="remarks"></a>コメント

**_aligned_offset_malloc**入れ子になった要素に対するアラインメントが必要な場所の状況で役に立ちますの例では、入れ子になったクラスに対するアラインメントが必要です。

**_aligned_offset_malloc**に基づく**malloc**。 詳細については、を参照してください[malloc](malloc.md)です。

**_aligned_offset_malloc**がマークされている`__declspec(noalias)`と`__declspec(restrict)`、グローバル変数を変更せず、関数が保証されると、返されるポインターがエイリアス化されないを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」、および「[restrict](../../cpp/restrict.md)」を参照してください。

この関数は、設定**errno**に**ENOMEM**メモリの割り当てが失敗するか、要求されたサイズより大きい場合 **_HEAP_MAXREQ**です。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。 また、 **_aligned_offset_malloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*ゼロ以外、この関数によって呼び出されます、無効なパラメーター ハンドラーを」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**NULL**設定と**errno**に**EINVAL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
