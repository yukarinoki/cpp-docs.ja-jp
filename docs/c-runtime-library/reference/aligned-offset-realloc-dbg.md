---
description: '詳細については、次を参照してください: _aligned_offset_realloc_dbg'
title: _aligned_offset_realloc_dbg
ms.date: 11/04/2016
api_name:
- _aligned_offset_realloc_dbg
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
- aligned_offset_realloc_dbg
- _aligned_offset_realloc_dbg
helpviewer_keywords:
- aligned_offset_realloc_dbg function
- _aligned_offset_realloc_dbg function
ms.assetid: 64e30a12-887e-453b-aea8-aed793fca9d8
ms.openlocfilehash: 02d7227aca01c1c12f62665e4037c19609e044c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97312527"
---
# <a name="_aligned_offset_realloc_dbg"></a>_aligned_offset_realloc_dbg

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

*配置*<br/>
アラインメント値。2 の整数乗である必要があります。

*offset*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*filename*<br/>
**Aligned_offset_realloc** 操作を要求したソースファイルの名前へのポインターまたは **NULL**。

*linenumber*<br/>
**Aligned_offset_realloc** 操作が要求されたソースファイル内の行番号または **NULL**。

## <a name="return-value"></a>戻り値

**_aligned_offset_realloc_dbg** は、再割り当てされた (移動された可能性がある) メモリブロックへの void ポインターを返します。 サイズが0でバッファー引数が **null** でない場合、またはブロックを指定されたサイズに拡張するのに十分なメモリがない場合、戻り値は **null** になります。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

## <a name="remarks"></a>解説

**_aligned_offset_realloc_dbg** は、 [_aligned_offset_realloc](aligned-offset-realloc.md) 関数のデバッグバージョンです。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_aligned_offset_realloc_dbg** の各呼び出しは **_aligned_offset_realloc** への呼び出しに限定されます。 **_Aligned_offset_realloc** と **_aligned_offset_realloc_dbg** はどちらもベースヒープ内のメモリブロックを再割り当てしますが、 **_aligned_offset_realloc_dbg** にはいくつかのデバッグ機能があります。リークをテストするための、ブロックのユーザー部分の両側のバッファーと、  / 割り当て要求の起点を特定するための filename *linenumber* information です。 ブロックの型パラメーターを使用して特定の割り当ての種類を追跡することは、固定された割り当てのデバッグ機能としてサポートされていません。 配置された割り当ては、_NORMAL_BLOCK ブロック型として表示されます。

[_Aligned_offset_malloc](aligned-offset-malloc.md)と同様に、 **_aligned_offset_realloc_dbg** を使用すると、構造体内のオフセットに構造体を配置できます。

**_realloc_dbg** は、要求された *newSize* よりも少し多くの領域を使用して、指定されたメモリブロックを再割り当てします。 *newSize* が、最初に割り当てられたメモリブロックのサイズより大きいか小さい可能性があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。

メモリ割り当てが失敗した場合、または要求されたサイズが **_HEAP_MAXREQ** より大きい場合、この関数は **errno** を **ENOMEM** に設定します。 **Errno** の詳細については、「 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。 また、 **_aligned_offset_realloc_dbg** パラメーターを検証します。 *Alignment* が2の累乗でない場合、または *offset* が *size* 以上で0以外の場合、この関数は「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーを呼び出します。 実行の継続が許可された場合、この関数は **NULL** を返し、 **errno** を **EINVAL** に設定します。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロックの型とその使用方法については、「 [デバッグヒープ上のブロックの型](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_realloc_dbg**|\<crtdbg.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
