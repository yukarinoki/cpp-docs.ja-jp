---
title: _expand_dbg
ms.date: 11/04/2016
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
helpviewer_keywords:
- memory blocks, changing size
- expand_dbg function
- _expand_dbg function
ms.assetid: dc58c91f-72a8-48c6-b643-fe130fb6c1fd
ms.openlocfilehash: cc3aa2b7e39b52eb71ac10a9b5c4a221ba6fb70c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62288046"
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

*userData*<br/>
以前に割り当てられていたメモリ ブロックへのポインター。

*newSize*<br/>
ブロックのために要求する新しいサイズ (バイト単位)。

*blockType*<br/>
要求されたサイズ変更するブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**します。

*ファイル名*<br/>
拡張操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
展開操作が要求されたソース ファイル内の番号を行または**NULL**します。

*Filename*と*linenumber*ときにパラメーターが使用可能なだけ **_expand_dbg**が明示的に呼び出された、または[_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)プリプロセッサ定数が定義されています。

## <a name="return-value"></a>戻り値

正常に完了 **_expand_dbg**サイズを変更したメモリ ブロックへのポインターを返します。 メモリが移動されないため、アドレスは userData と同じです。 返されますかどうか、エラーが発生しましたまたはブロックは、要求されたサイズに展開されませんでした、 **NULL**します。 失敗した場合、 **errno**エラーの性質に関するオペレーティング システムからの情報とは。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。

## <a name="remarks"></a>Remarks

**_Expand_dbg**関数は、_ のデバッグ バージョン[展開](expand.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_expand_dbg**への呼び出しに減少 **_expand**します。 両方 **_expand**と **_expand_dbg**ベースのヒープにメモリ ブロックをサイズ変更が **_expand_dbg**はいくつかのデバッグ機能を提供: ユーザーのいずれかの側バッファー特定の割り当ての種類を追跡するためのブロック型パラメーターのリークをテストするブロックの部分と*filename*/*linenumber*の起点を特定する情報割り当て要求。

**_expand_dbg** 、要求したよりも少し多い領域を指定されたメモリ ブロックのサイズを変更*newSize*します。 *newSize*最初に割り当てられたメモリ ブロックのサイズよりも小さいか大きい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 サイズ変更は、元のメモリ ブロックを拡張または縮小することで実現されます。 **_expand_dbg**同様、メモリ ブロックを移動しません、 [_realloc_dbg](realloc-dbg.md)関数。

ときに*newSize*がメモリ ブロックのサイズが展開されて、元のブロックを超えています。 要求されたサイズに対応するために、メモリ ブロックを拡張できない場合、拡張時に**NULL**が返されます。 ときに*newSize*が元のブロック、新しいサイズになるまで、メモリ ブロックのサイズを縮小はよりも少ない。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

この関数は、パラメーターを検証します。 場合 *_expand*が null ポインターのサイズよりも大きい場合、または **_HEAP_MAXREQ**、」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL** 、関数を返します**NULL**します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
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
