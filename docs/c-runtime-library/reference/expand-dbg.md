---
title: _expand_dbg | Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _expand_dbg
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
- expand_dbg
- _expand_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 023bda761454a6a1e18ce68c8e7576af2759abbf
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="expanddbg"></a>_expand_dbg

ブロックの拡張や縮小によって、ヒープ内の指定されたメモリのブロックをサイズ変更します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void *_expand_dbg(
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
ブロックのために要求する新しいサイズ (バイト単位)。

*blockType*<br/>
要求されたサイズ変更されたブロックの型: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**です。

*ファイル名*<br/>
拡張操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
展開操作が要求されたソース ファイルの数の行または**NULL**です。

*Filename*と*linenumber*パラメーターは、のみ使用可能な場合に **_expand_dbg**が明示的に呼び出された、または[_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)プリプロセッサ定数が定義されています。

## <a name="return-value"></a>戻り値

正常に終了、 **_expand_dbg**サイズを変更したメモリ ブロックへのポインターを返します。 メモリが移動されないため、アドレスは userData と同じです。 返しますエラーが発生したか、ブロックは、要求されたサイズに展開されませんでした、 **NULL**です。 失敗した場合、 **errno**エラーの性質に関するオペレーティング システムからの情報はします。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。

## <a name="remarks"></a>コメント

**_Expand_dbg**関数は、_ のデバッグ バージョン[展開](expand.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_expand_dbg**への呼び出しに減少 **_expand**です。 両方 **_expand**と **_expand_dbg**はベース ヒープ内のメモリ ブロックをサイズ変更が **_expand_dbg**はいくつかのデバッグ機能を提供しますユーザーの両側のバッファー。特定の割り当ての種類を追跡するブロック型パラメーター、リークをテストするブロックの部分と*filename*/*linenumber*の起点を特定する情報割り当て要求します。

**_expand_dbg** 、要求したよりも少し多い領域を持つ指定されたメモリ ブロックをサイズ変更*newSize*です。 *newSize*大きいか、最初に割り当てられたメモリ ブロックのサイズよりも小さい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 サイズ変更は、元のメモリ ブロックを拡張または縮小することで実現されます。 **_expand_dbg**同様、メモリ ブロックを移動しません、 [_realloc_dbg](realloc-dbg.md)関数。

ときに*newSize*元のブロック サイズ、メモリ ブロックが展開されているよりも大きいです。 メモリ ブロックを要求されたサイズに合わせて拡張できない場合、拡張時に**NULL**が返されます。 ときに*newSize*が元のブロック サイズ、メモリ ブロックが契約を新しいサイズを取得するまでよりも少ない。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

この関数は、パラメーターを検証します。 場合 *_expand*が null ポインターのサイズよりも大きい場合、または **_HEAP_MAXREQ**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**です。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_expand_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

```C
// crt_expand_dbg.c
//
// This program allocates a block of memory using _malloc_dbg
// and then calls _msize_dbg to display the size of that block.
// Next, it uses _expand_dbg to expand the amount of
// memory used by the buffer and then calls _msize_dbg again to
// display the new amount of memory allocated to the buffer.
//

#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
#include <crtdbg.h>

int main( void )
{
   long *buffer;
   size_t size;

   // Call _malloc_dbg to include the filename and line number
   // of our allocation request in the header
   buffer = (long *)_malloc_dbg( 40 * sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );
   if( buffer == NULL )
      exit( 1 );

   // Get the size of the buffer by calling _msize_dbg
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _malloc_dbg of 40 longs: %u\n", size );

   // Expand the buffer using _expand_dbg and show the new size
   buffer = (long *)_expand_dbg( buffer, size + sizeof(long),
                                 _NORMAL_BLOCK, __FILE__, __LINE__ );

   if( buffer == NULL )
      exit( 1 );
   size = _msize_dbg( buffer, _NORMAL_BLOCK );
   printf( "Size of block after _expand_dbg of 1 more long: %u\n",
           size );

   free( buffer );
   exit( 0 );
}
```

```Output
Size of block after _malloc_dbg of 40 longs: 160
Size of block after _expand_dbg of 1 more long: 164
```

## <a name="comment"></a>コメント

このプログラムの出力は、すべてのセクションを拡張するためのコンピューターの能力によって異なります。 すべてのセクションが展開される場合、出力は出力セクションに反映されます。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
