---
title: _aligned_realloc_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _aligned_realloc_dbg
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
- aligned_realloc_dbg
- _aligned_realloc_dbg
dev_langs:
- C++
helpviewer_keywords:
- _aligned_realloc_dbg function
- aligned_realloc_dbg function
ms.assetid: 8aede920-991e-44cd-867f-83dc2165db47
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1fd5854bc18cecda1fd3ffee4f28ec2fa5d2a68a
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34451668"
---
# <a name="alignedreallocdbg"></a>_aligned_realloc_dbg

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックのサイズを変更します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void * _aligned_realloc_dbg(
   void *memblock,
   size_t size,
   size_t alignment,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>パラメーター

*_expand*<br/>
現在のメモリ ブロック ポインター。

*size*<br/>
要求されたメモリ割り当てのサイズ。

*alignment*<br/>
アラインメント値。2 の整数乗である必要があります。

*ファイル名*<br/>
要求したソース ファイルの名前へのポインター、 **realloc**操作または**NULL**です。

*行番号*<br/>
ソース ファイルの数の行で、 **realloc**操作が要求されましたまたは**NULL**です。

## <a name="return-value"></a>戻り値

**_aligned_realloc_dbg**再割り当てされた (移動された可能性のある) メモリ ブロックへの void ポインターを返します。 戻り値は**NULL**サイズが 0 と、バッファー引数がないかどうかは**NULL**、特定のサイズにブロックを拡張するための十分な使用可能なメモリがない場合またはします。 最初の場合には、元のブロックは解放されます。 2 番目の場合には、元のブロックは変更されません。 戻り値は、どの型のオブジェクトを格納する場合でも適切なアラインメントが保証されるストレージ領域を指します。 void 以外の型へのポインターを取得するには、戻り値の型キャストを使用します。

メモリを再割り当てしてブロックのアラインメントを変更すると、エラーになります。

## <a name="remarks"></a>コメント

**_aligned_realloc_dbg**のデバッグ バージョンは、 [_aligned_realloc](aligned-realloc.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_realloc_dbg**への呼び出しに減少 **_aligned_realloc**です。 両方 **_aligned_realloc**と **_aligned_realloc_dbg**はベース ヒープ内にメモリ ブロックを再割り当てしますが、 **_aligned_realloc_dbg**はいくつかのデバッグ機能を提供: 特定の割り当ての種類を追跡するブロック型パラメーター、リークをテストする、ブロックのユーザー部分の両側のバッファーと*filename*/*linenumber*割り当て要求の起点を特定する情報です。

**_aligned_realloc_dbg** 、要求したよりも少し多い領域を持つ指定されたメモリ ブロックを再割り当て*newSize*です。 *newSize*大きいか、最初に割り当てられたメモリ ブロックのサイズよりも小さい場合があります。 追加の領域は、デバッグ メモリ ブロックをリンクし、アプリケーションにデバッグ ヘッダー情報と上書きバッファーを提供するために、デバッグ ヒープ マネージャーによって使用されます。 再割り当てによって、元のメモリ ブロックがヒープ内の別の位置に移動されたり、メモリ ブロックのサイズが変わったりする場合があります。 メモリ ブロックが移動される場合、元のブロックの内容は上書きされます。

**_aligned_realloc_dbg**設定**errno**に**ENOMEM**メモリ割り当てに失敗した場合、または (前に説明したオーバーヘッドを含む) に必要なメモリの量を上回る場合 **_HEAP_MAXREQ**です。 このエラー コードと他のエラーコードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

また、 **_aligned_realloc_dbg**パラメーターを検証します。 場合*配置*累乗 2 のこの関数によって呼び出されます、無効なパラメーター ハンドラーを」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行は継続許可されたかどうか、この関数を返します**NULL**設定と**errno**に**EINVAL**です。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_aligned_realloc_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
