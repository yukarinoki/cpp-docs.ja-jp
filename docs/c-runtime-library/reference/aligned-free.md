---
title: _aligned_free | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_free
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
- aligned_free
- _aligned_free
dev_langs:
- C++
helpviewer_keywords:
- _aligned_free function
- aligned_free function
ms.assetid: ed1ce952-cdfc-4682-85cc-f75d4101603d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e18c02909c247af4066033fc3e3633db74327f55
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44102643"
---
# <a name="alignedfree"></a>_aligned_free

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックを解放します。

## <a name="syntax"></a>構文

```C
void _aligned_free (
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*_expand*  
`_aligned_malloc` または `_aligned_offset_malloc` 関数に返されたメモリ ブロックへのポインター。

## <a name="remarks"></a>Remarks

**_aligned_free**がマークされている`__declspec(noalias)`、グローバル変数を変更することがなく、関数が保証されることを意味します。 詳細については、「[noalias](../../cpp/noalias.md)」を参照してください。

この関数は、他の _aligned CRT 関数とは異なり、パラメーターを検証しません。 場合 *_expand* NULL ポインターでは、この関数がないアクションを実行だけです。 この関数は `errno` を変更せず、無効なパラメーター ハンドラーを呼び出しません。 以前にメモリのブロックを割り当てるために _aligned 関数を使用しなかったために関数でエラーが発生する場合、または何らかの予期しない災害によってメモリの不整合が発生する場合、関数は [_RPT、_RPTF、_RPTW、_RPTFW のマクロ](rpt-rptf-rptw-rptfw-macros.md)からデバッグ レポートを生成します。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_free**|\<malloc.h>|

## <a name="example"></a>例

詳細については、「[_aligned_malloc](aligned-malloc.md)」を参照してください。

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)  