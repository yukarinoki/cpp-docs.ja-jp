---
title: _aligned_offset_realloc_dbg
ms.date: 11/04/2016
apiname:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
ms.openlocfilehash: e5ffb37227e1e20f32e065290056da05e7dcd065
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625863"
---
# <a name="alignedoffsetreallocdbg"></a>_aligned_offset_realloc_dbg

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
現在のメモリ ブロック ポインター。

*size*<br/>
メモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*ファイル名*<br/>
要求したソース ファイルの名前へのポインター、 **aligned_offset_realloc**操作または**NULL**します。

*行番号*<br/>
ソース ファイルの数の行で、 **aligned_offset_realloc**操作の要求または**NULL**します。

## <a name="return-value"></a>戻り値

**_aligned_offset_realloc_dbg**再割り当てされた (および移動) のメモリ ブロックに void ポインターを返します。 戻り値は**NULL** 、サイズが 0 のかどうか、およびバッファー引数ではありません**NULL**、または指定されたサイズにブロックを拡張するための十分な使用可能なメモリがない場合。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

## <a name="remarks"></a>Remarks

**_aligned_offset_realloc_dbg**のデバッグ バージョンです、 [_aligned_offset_realloc](aligned-offset-realloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_offset_realloc_dbg**への呼び出しに減少 **_aligned_offset_realloc**します。 両方 **_aligned_offset_realloc**と **_aligned_offset_realloc_dbg**ベースのヒープにメモリ ブロックを再割り当てが **_aligned_offset_realloc_dbg**対応していますいくつかのデバッグ機能: リーク、特定の割り当ての種類を追跡するためのブロック型パラメーターをテストする、ブロックのユーザー部分の両側のバッファーと*filename*/*linenumber*割り当て要求の起点を特定する情報。

ような[_aligned_offset_malloc](aligned-offset-malloc.md)、 **_aligned_offset_realloc_dbg**では構造内のオフセットに配置する構造。

**_realloc_dbg** 、要求したよりも少し多い領域を指定されたメモリ ブロックを再割り当て*newSize*します。 *newSize*最初に割り当てられたメモリ ブロックのサイズよりも小さいか大きい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。

この関数は、設定**errno**に**ENOMEM** 、メモリの割り当てに失敗した場合、または要求されたサイズより大きい場合 **_HEAP_MAXREQ**します。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)します。 また、 **_aligned_offset_realloc_dbg**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*がより大きいまたは等しい*サイズ*0 以外の場合、この関数は無効なパラメーター ハンドラーを呼び出します」の説明に従って、[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 かどうかは、引き続き実行が許可された、この関数を返します**NULL**設定と**errno**に**EINVAL**します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
