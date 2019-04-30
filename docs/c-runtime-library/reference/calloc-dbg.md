---
title: _calloc_dbg
ms.date: 11/04/2016
apiname:
- _calloc_dbg
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
- _calloc_dbg
- calloc_dbg
helpviewer_keywords:
- _calloc_dbg function
- calloc_dbg function
ms.assetid: 7f62c42b-eb9f-4de5-87d0-df57036c87de
ms.openlocfilehash: c525aa2f19b39ba3cb8304c59c96196707ad859c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340863"
---
# <a name="callocdbg"></a>_calloc_dbg

デバッグ ヘッダーと上書きバッファー用の追加の領域を持つ多数のメモリ ブロックをヒープに割り当てます (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void *_calloc_dbg(
   size_t num,
   size_t size,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*number*<br/>
要求するメモリ ブロックの数。

*size*<br/>
要求する各メモリ ブロックのサイズ (バイト)。

*blockType*<br/>
要求されたメモリ ブロックの種類: **_CLIENT_BLOCK**または **_NORMAL_BLOCK**します。

割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

*ファイル名*<br/>
割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**します。

*行番号*<br/>
割り当て操作が要求されたソース ファイル内の番号を行または**NULL**します。

*Filename*と*linenumber*ときにパラメーターが使用可能なだけ **_calloc_dbg**が明示的に呼び出された、または[_CRTDBG_MAP_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md)プリプロセッサ定数が定義されています。

## <a name="return-value"></a>戻り値

正常に完了する、この関数、最後に割り当てられたメモリ ブロックのユーザー部分へのポインターを返します、新しいハンドラー関数を呼び出し、または返します**NULL**します。 戻る動作の詳細については、「解説」のセクションを参照してください。 新しいハンドラー関数がどのように使用されるかの詳細については、[calloc](calloc.md) 関数を参照してください。

## <a name="remarks"></a>Remarks

**_calloc_dbg**のデバッグ バージョンです、 [calloc](calloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_calloc_dbg**への呼び出しに減少**calloc**します。 両方**calloc**と **_calloc_dbg**割り当てる*数*ベースのヒープ内のメモリ ブロックしますが、 **_calloc_dbg**いくつかのデバッグを提供しています機能:

- リークをテストするための、ブロックのユーザー部分の両側のバッファー。

- 特定の割り当ての種類を追跡するためのブロック型パラメーター。

- *ファイル名*/*linenumber*割り当て要求の起点を特定する情報。

**_calloc_dbg**各メモリ ブロックを要求したよりも少し多い領域を割り当てます*サイズ*します。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 ブロックが割り当てられると、ブロックのユーザー部分には値 0xCD が設定され、各上書きバッファーには 0xFD が設定されます。

**_calloc_dbg**設定**errno**に**ENOMEM**メモリ割り当てが失敗した場合。**EINVAL** (以前に説明したオーバーヘッドを含む) に必要なメモリの量を超えたかどうかに返される **_HEAP_MAXREQ**します。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_calloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_callocd.c
// This program uses _calloc_dbg to allocate space for
// 40 long integers. It initializes each element to zero.

#include <stdio.h>
#include <malloc.h>
#include <crtdbg.h>

int main( void )
{
    long *bufferN, *bufferC;

    // Call _calloc_dbg to include the filename and line number
    // of our allocation request in the header and also so we can
    // allocate CLIENT type blocks specifically
    bufferN = (long *)_calloc_dbg( 40, sizeof(long), _NORMAL_BLOCK, __FILE__, __LINE__ );
    bufferC = (long *)_calloc_dbg( 40, sizeof(long), _CLIENT_BLOCK, __FILE__, __LINE__ );
    if( bufferN != NULL && bufferC != NULL )
        printf( "Allocated memory successfully\n" );
    else
        printf( "Problem allocating memory\n" );

    / _free_dbg must be called to free CLIENT type blocks
    free( bufferN );
    _free_dbg( bufferC, _CLIENT_BLOCK );
}
```

```Output
Allocated memory successfully
```

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[calloc](calloc.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
