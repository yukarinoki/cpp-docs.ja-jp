---
title: _CrtDumpMemoryLeaks
ms.date: 11/04/2016
apiname:
- _CrtDumpMemoryLeaks
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
- CRTDBG_LEAK_CHECK_DF
- CRTDBG_CHECK_CRT_DF
- _CRTDBG_LEAK_CHECK_DF
- CrtDumpMemoryLeaks
- _CrtDumpMemoryLeaks
- _CRTDBG_CHECK_CRT_DF
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
ms.openlocfilehash: baf4f8d8234ba744acda20541d37bbc3ed076678
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339456"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

メモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>戻り値

**_CrtDumpMemoryLeaks**メモリ リークが見つかった場合は TRUE を返します。 それ以外の場合、関数は FALSE を返します。

## <a name="remarks"></a>Remarks

**_CrtDumpMemoryLeaks**関数は、プログラムの実行が開始されてから、メモリ リークが発生したかどうかを決定します。 メモリ リークが見つかると、ヒープ内のすべてのオブジェクトのデバッグ ヘッダー情報が、ユーザーが判読できる形式でダンプされます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtDumpMemoryLeaks**プリプロセス時に削除されます。

**_CrtDumpMemoryLeaks**が頻繁に、アプリケーションによって割り当てられたすべてのメモリが解放されたことを確認するプログラムの実行の最後に呼び出されます。 関数で呼び出せるように自動的にプログラムの終了時の有効化、 **_CRTDBG_LEAK_CHECK_DF**のビット フィールド、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグを使用して、 [_CrtSetDbgFlag](crtsetdbgflag.md)関数。

**_CrtDumpMemoryLeaks**呼び出し[_CrtMemCheckpoint](crtmemcheckpoint.md)ヒープの現在の状態を取得し、解放されていないブロックの状態をスキャンします。 未解放のブロックが発生した場合に **_CrtDumpMemoryLeaks**呼び出し[_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md)プログラムの実行開始からヒープに割り当てられたすべてのオブジェクトの情報をダンプします。

既定では、内部 C ランタイム ブロック (**_CRT_BLOCK**) メモリ ダンプ操作には含まれません。 [_CrtSetDbgFlag](crtsetdbgflag.md)を有効にする関数を使用できます、 **_CRTDBG_CHECK_CRT_DF**のビット **_crtDbgFlag**にこれらのブロックをリーク検出プロセスに含めます。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法の例については **_CrtDumpMemoryLeaks**を参照してください[crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)します。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
