---
title: _free_dbg | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _free_dbg
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
- _free_dbg
- free_dbg
dev_langs:
- C++
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aa485eea6f0ffda05b0ef33a808d5ec837255514
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="freedbg"></a>_free_dbg

ヒープ内のメモリ ブロックを解放します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>パラメーター

*userData*解放される、割り当てられたメモリ ブロックへのポインター。

*blockType*解放するには、割り当てられたメモリ ブロックの型: **_CLIENT_BLOCK**、 **_NORMAL_BLOCK**、または **_IGNORE_BLOCK**です。

## <a name="remarks"></a>コメント

**_Free_dbg**関数は、デバッグ バージョンの[空き](free.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_free_dbg**への呼び出しに減少**空き**です。 両方**空き**と **_free_dbg**はベース ヒープのメモリ ブロックを解放が **_free_dbg**は 2 つのデバッグ機能を提供: ブロックをヒープの解放を保持する機能メモリ不足の状態と種類の特定の割り当てを解放するブロック型パラメーターをシミュレートするリンクの一覧です。

**_free_dbg**解放操作を実行する前に指定されたすべてのファイルおよびブロックの位置では、有効性チェックを実行します。 アプリケーションは、この情報を提供する必要はありません。 メモリ ブロックが解放されると、デバッグ ヒープ マネージャーはユーザー部分の前後のバッファーの整合性を自動的にチェックし、それらのバッファーが上書きされていた場合はエラー レポートを発行します。 場合、 **_CRTDBG_DELAY_FREE_MEM_DF**のビット フィールド、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグが設定されて、解放されたブロックが割り当てられている値 0 xdd、格納、 **_FREE_BLOCK**ブロック型、およびメモリ ブロックのヒープのリンク リストに保持されます。

場合は、メモリの解放でエラーが発生した**errno**エラーの性質に関するオペレーティング システムからの情報に設定します。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

使用する方法のサンプルについては **_free_dbg**を参照してください[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)です。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
