---
title: _aligned_offset_malloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_malloc_dbg
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
apitype: DLLExport
f1_keywords:
- _aligned_offset_malloc_dbg
- aligned_offset_malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_offset_malloc_dbg function
- aligned_offset_malloc_dbg function
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7e0b0838f75e8fa95d19ed3abfe13b014157a217
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="alignedoffsetmallocdbg"></a>_aligned_offset_malloc_dbg

指定された配置境界にメモリを割り当てます (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_malloc_dbg(
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
要求されたメモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*ファイル名*<br/>
割り当て操作を要求したソース ファイル名へのポインターまたは NULL。

*行番号*<br/>
割り当て操作が要求されたソース ファイル内の行番号または NULL。

## <a name="return-value"></a>戻り値

割り当てられたメモリ ブロックへのポインターまたは**NULL**場合は、操作に失敗しました。

## <a name="remarks"></a>コメント

**_aligned_offset_malloc_dbg**のデバッグ バージョンは、 [_aligned_offset_malloc](aligned-offset-malloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_offset_malloc_dbg**への呼び出しに減少 **_aligned_offset_malloc**です。 両方 **_aligned_offset_malloc**と **_aligned_offset_malloc_dbg**はベース ヒープ内のメモリ ブロックを割り当てますが、 **_aligned_offset_malloc_dbg**いくつかの操作を提供していますデバッグ機能: リークを特定の割り当ての種類を追跡するブロック型パラメーターをテストする、ブロックのユーザー部分の両側のバッファーと*filename*/*linenumber*割り当て要求の起点を特定する情報。

**_aligned_offset_malloc_dbg** 、要求したよりも少し多い領域を持つメモリ ブロックを割り当てます*サイズ*です。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

**_aligned_offset_malloc_dbg**入れ子になった要素に対するアラインメントが必要な場所の状況で役に立ちますの例では、入れ子になったクラスに対するアラインメントが必要です。

**_aligned_offset_malloc_dbg**に基づく**malloc**。 詳細については、を参照してください[malloc](malloc.md)です。

この関数は、設定**errno**に**ENOMEM**メモリの割り当てが失敗するか、要求されたサイズより大きい場合 **_HEAP_MAXREQ**です。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。 また、 **_aligned_offset_malloc**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*ゼロ以外、この関数によって呼び出されます、無効なパラメーター ハンドラーを」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**NULL**設定と**errno**に**EINVAL**です。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_malloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
