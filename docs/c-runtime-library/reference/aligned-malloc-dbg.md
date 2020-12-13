---
description: '詳細については、次を参照してください: _aligned_malloc_dbg'
title: _aligned_malloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_malloc_dbg
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _aligned_malloc_dbg
- aligned_malloc_dbg
helpviewer_keywords:
- aligned_malloc_dbg function
- _aligned_malloc_dbg function
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
ms.openlocfilehash: dc593ee827bb5e3453695c5e35816116854d0460
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334280"
---
# <a name="_aligned_malloc_dbg"></a>_aligned_malloc_dbg

デバッグ ヘッダーと上書きバッファー用の追加の領域を持つメモリを、指定された配置境界に割り当てます (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_malloc_dbg(
    size_t size,
    size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
要求されたメモリ割り当てのサイズ。

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*filename*<br/>
割り当て操作を要求したソース ファイル名へのポインターまたは NULL。

*linenumber*<br/>
割り当て操作が要求されたソース ファイル内の行番号または NULL。

## <a name="return-value"></a>戻り値

割り当てられたメモリブロックへのポインター。操作が失敗した場合は NULL。

## <a name="remarks"></a>解説

**_aligned_malloc_dbg** は、 [_aligned_malloc](aligned-malloc.md) 関数のデバッグバージョンです。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_aligned_malloc_dbg** の各呼び出しはの呼び出しに限定され `_aligned_malloc` ます。 `_aligned_malloc`と **_aligned_malloc_dbg** は、ベースヒープ内にメモリブロックを割り当てますが、 **_aligned_malloc_dbg** はいくつかのデバッグ機能を提供します。リークをテストするために、ブロックのユーザー部分の両側のバッファーと、割り当て要求の発生元を特定するための *ファイル名* / *linenumber* 情報です。 ブロックの型パラメーターを使用して特定の割り当ての種類を追跡することは、固定された割り当てのデバッグ機能としてサポートされていません。 配置された割り当ては、_NORMAL_BLOCK ブロック型として表示されます。

**_aligned_malloc_dbg** は、要求された *サイズ* よりも若干多くの領域を使用してメモリブロックを割り当てます。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

 `errno` `ENOMEM` メモリ割り当てが失敗した場合、または必要なメモリの量 (前に説明したオーバーヘッドを含む) がを超えた場合、_aligned_malloc_dbg はをに設定 `_HEAP_MAXREQ` します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、 **_aligned_malloc_dbg** パラメーターを検証します。 *Alignment* が2の累乗でない場合、または *size* が0の場合、この関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は NULL を返し、 `errno` をに設定 `EINVAL` します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロックの型とその使用方法については、「 [デバッグヒープ上のブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_malloc_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)
