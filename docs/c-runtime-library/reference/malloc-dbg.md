---
title: _malloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _malloc_dbg
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
- malloc_dbg
- _malloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- malloc_dbg function
- memory allocation
- _malloc_dbg function
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: ebc1ff83840631074f04704e6df2a88437b8cc71
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451785"
---
# <a name="mallocdbg"></a>_malloc_dbg

デバッグ ヘッダーと上書きバッファー用の追加の領域を持つメモリ ブロックをヒープに割り当てます (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void *_malloc_dbg(
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*size*<br/>
要求するメモリ ブロックのサイズ (バイト単位)。

*blockType*<br/>
要求されたメモリ ブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
割り当て操作が要求されたソース ファイルの数の行または**NULL**です。

*Filename*と*linenumber*パラメーターは、のみ使用可能な場合に **_malloc_dbg**が明示的に呼び出された、または[_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)プリプロセッサ定数が定義されています。

## <a name="return-value"></a>戻り値

正常終了した場合、この関数、割り当てられたメモリ ブロックのユーザー部分へのポインターを返します、新しいハンドラー関数を呼び出し、またはを返します**NULL**です。 戻る動作の詳細については、後の「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[malloc](malloc.md) 関数を参照してください。

## <a name="remarks"></a>コメント

**_malloc_dbg**のデバッグ バージョンは、 [malloc](malloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_malloc_dbg**への呼び出しに減少**malloc**です。 両方**malloc**と **_malloc_dbg**はベース ヒープ内のメモリ ブロックを割り当てますが、 **_malloc_dbg**いくつかのデバッグ機能を提供しています: ユーザーの両側のバッファー特定の割り当ての種類を追跡するブロック型パラメーター、リークをテストするブロックの部分と*filename*/*linenumber*の起点を特定する情報割り当て要求します。

**_malloc_dbg** 、要求したよりも少し多い領域を持つメモリ ブロックを割り当てます*サイズ*です。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

**_malloc_dbg**設定**errno**に**ENOMEM**メモリ割り当てに失敗した場合、または (前に説明したオーバーヘッドを含む) に必要なメモリの量を上回る場合 **_HEAP_MAXREQ**です。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_malloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法のサンプルについては **_malloc_dbg**を参照してください[crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)です。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[malloc](malloc.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
[_calloc_dbg](calloc-dbg.md)<br/>
