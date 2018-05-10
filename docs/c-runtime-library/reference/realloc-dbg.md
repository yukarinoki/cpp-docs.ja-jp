---
title: _realloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _realloc_dbg
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
- _realloc_dbg
- realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- reallocating memory blocks
- realloc_dbg function
- memory blocks, reallocating
- memory, reallocating
- _realloc_dbg function
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 91d04e78c6f3521c56cd74968a761a2d436e36bf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="reallocdbg"></a>_realloc_dbg

ブロックの移動やサイズ変更によって、ヒープ内の指定されたメモリのブロックを再割り当てします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void *_realloc_dbg(
   void *userData,
   size_t newSize,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*UserData*<br/>
以前に割り当てられていたメモリ ブロックへのポインター。

*newSize*<br/>
再割り当てされるブロックのために要求するサイズ (バイト)。

*blockType*<br/>
再割り当てされるブロックの型を要求しました: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
要求したソース ファイルの名前へのポインター、 **realloc**操作または NULL。

*行番号*<br/>
ソース ファイルの数の行で、 **realloc**操作が要求されているか NULL です。

*Filename*と*linenumber*パラメーターは、のみ使用可能な場合に **_realloc_dbg**が明示的に呼び出された、または[_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)プリプロセッサ定数が定義されています。

## <a name="return-value"></a>戻り値

正常に終了した場合、この関数は再割り当てされたメモリ ブロックのユーザー部分へのポインターを返すか、新しいハンドラー関数を呼び出すか、NULL を返します。 戻る動作の詳細については、後の「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[realloc](realloc.md) 関数を参照してください。

## <a name="remarks"></a>コメント

**_realloc_dbg**のデバッグ バージョンは、 [realloc](realloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_realloc_dbg**への呼び出しに減少**realloc**です。 両方**realloc**と **_realloc_dbg**はベース ヒープ内にメモリ ブロックを再割り当てしますが、 **_realloc_dbg**はいくつかのデバッグ機能を提供しますの両側のバッファー、。特定の割り当ての種類を追跡するブロック型パラメーター、リークをテストするブロックのユーザー部分と*filename*/*linenumber*の起点を特定する情報割り当て要求します。

**_realloc_dbg** 、要求したよりも少し多い領域を持つ指定されたメモリ ブロックを再割り当て*newSize*です。 *newSize*大きいか、最初に割り当てられたメモリ ブロックのサイズよりも小さい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。

**_realloc_dbg**設定**errno**に**ENOMEM**メモリ割り当てに失敗した場合、または (前に説明したオーバーヘッドを含む) に必要なメモリの量を上回る場合 **_HEAP_MAXREQ**です。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_realloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

「[_msize_dbg](msize-dbg.md)」のトピックの例を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
