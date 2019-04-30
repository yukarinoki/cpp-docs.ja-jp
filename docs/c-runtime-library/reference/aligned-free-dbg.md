---
title: _aligned_free_dbg
ms.date: 11/04/2016
apiname:
- _aligned_free_dbg
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
- _aligned_free_dbg
- aligned_free_dbg
helpviewer_keywords:
- _aligned_free_dbg function
- aligned_free_dbg function
ms.assetid: eb0cb3c8-0992-4db8-bac3-65f1b8311ca6
ms.openlocfilehash: f51b9b9573ab2e23a0a60979c55a33d2e5cff747
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62341900"
---
# <a name="alignedfreedbg"></a>_aligned_free_dbg

[_aligned_malloc](aligned-malloc.md) または [_aligned_offset_malloc](aligned-offset-malloc.md) で割り当てられたメモリ ブロックを解放します (デバッグのみ)。

## <a name="syntax"></a>構文

```C
void _aligned_free_dbg(
   void *memblock
);
```

### <a name="parameters"></a>パラメーター

*memblock*<br/>
返されたメモリ ブロックへのポインター、 [_aligned_malloc](aligned-malloc.md)または[_aligned_offset_malloc](aligned-offset-malloc.md)関数。

## <a name="remarks"></a>Remarks

**_Aligned_free_dbg**関数のデバッグ バージョンは、 [_aligned_free](aligned-free.md)関数。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない呼び出しごとに **_aligned_free_dbg**への呼び出しに減少`_aligned_free`します。 両方`_aligned_free`と **_aligned_free_dbg**ベースのヒープにメモリ ブロックを解放が **_aligned_free_dbg**対応のデバッグ機能: 解放されたを保持する機能ブロックをヒープのリンク リストメモリ不足の状態をシミュレートします。

**_aligned_free_dbg**解放操作を実行する前に指定したすべてのファイルとブロックの場所の有効性チェックを実行します。 アプリケーションは、この情報を提供する必要はありません。 メモリ ブロックが解放されると、デバッグ ヒープ マネージャーはユーザー部分の前後のバッファーの整合性を自動的にチェックし、それらのバッファーが上書きされていた場合はエラー レポートを発行します。 _CRTDBG_DELAY_FREE_MEM_DF、ビット フィールドの場合、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグが設定されて、解放されたブロックは値 0 xdd 値を入力、_FREE_BLOCK ブロックの型が割り当てられているメモリ ブロックのヒープのリンクされたリストに保持されます。

メモリの解放でエラーが発生すると、エラーの性質に関するオペレーティング システムからの情報が `errno` に設定されます。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 割り当てブロック型と、それらがどのように使用されるかについては、「[デバッグ ヒープ上のメモリ ブロックの型](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。 標準で呼び出すヒープ関数と、アプリケーションのデバッグ ビルドで呼び出すデバッグ バージョンのヒープ関数との違いの詳細については、「[デバッグ バージョンのヒープ割り当て関数](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_aligned_free_dbg**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)