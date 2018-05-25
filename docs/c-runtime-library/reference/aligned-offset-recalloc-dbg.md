---
title: _aligned_offset_recalloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_offset_recalloc_dbg
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
- aligned_offset_recalloc_dbg
- _aligned_offset_recalloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- aligned_offset_recalloc_dbg function
- _aligned_offset_recalloc_dbg function
ms.assetid: 7ab719c3-77e0-4d2e-934f-01529d062fbf
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 02b920832d462c88c13d68525a1a4038cf6720f1
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
---
# <a name="alignedoffsetrecallocdbg"></a>_aligned_offset_recalloc_dbg

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更し、メモリを 0 に初期化します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_offset_recalloc_dbg(
   void *memblock,
   size_t num,
   size_t size,
   size_t alignment,
   size_t offset,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*_expand*<br/>
現在のメモリ ブロック ポインター。

*数*<br/>
要素の数。

*size*<br/>
各要素の長さ (バイト単位)。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*オフセット*<br/>
アラインメントを強制するためのメモリ割り当てへのオフセット。

*ファイル名*<br/>
再割り当て操作を要求したソース ファイルの名前へのポインターまたは**NULL**です。

*行番号*<br/>
Realloc 操作が要求されたソース ファイルの数の行または**NULL**です。

## <a name="return-value"></a>戻り値

**_aligned_offset_recalloc_dbg**再割り当てされた (移動された可能性のある) メモリ ブロックへの void ポインターを返します。 戻り値は**NULL**サイズが 0 と、バッファー引数がないかどうかは**NULL**、特定のサイズにブロックを拡張するための十分な使用可能なメモリがない場合またはします。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

## <a name="remarks"></a>コメント

**_aligned_offset_realloc_dbg**のデバッグ バージョンは、 [_aligned_offset_recalloc](aligned-offset-recalloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_offset_recalloc_dbg**への呼び出しに減少 **_aligned_offset_recalloc**です。 両方 **_aligned_offset_recalloc**と **_aligned_offset_recalloc_dbg**はベース ヒープ内にメモリ ブロックを再割り当てしますが、 **_aligned_offset_recalloc_dbg**対応いくつかのデバッグ機能: リークを特定の割り当ての種類を追跡するブロック型パラメーターをテストする、ブロックのユーザー部分の両側のバッファーと*filename*/*linenumber*割り当て要求の起点を特定する情報。

**_aligned_offset_realloc_dbg** 、要求したよりも少し多い領域を持つ指定されたメモリ ブロックを再割り当て*newSize*です。 *newSize*大きいか、最初に割り当てられたメモリ ブロックのサイズよりも小さい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。

この関数は、設定**errno**に**ENOMEM**メモリ割り当てに失敗した場合、または場合、要求されたサイズ (*数* * *サイズ*) よりも大きかった **_HEAP_MAXREQ**です。 詳細については**errno**を参照してください[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)です。 また、 **_aligned_offset_recalloc_dbg**パラメーターを検証します。 場合*配置*が 2 の累乗でない場合、または*オフセット*より大きいか、要求されたサイズに等しいと 0 以外の場合に」の説明に従って、この関数は、無効なパラメーター ハンドラーを呼び出します[パラメーター検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**NULL**設定と**errno**に**EINVAL**です。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_offset_recalloc_dbg**|\<malloc.h>|

## <a name="see-also"></a>関連項目

[データの整列](../../c-runtime-library/data-alignment.md)<br/>
