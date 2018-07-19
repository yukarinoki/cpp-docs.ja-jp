---
title: _CrtDumpMemoryLeaks | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- CrtDumpMemoryLeaks function
- CRTDBG_LEAK_CHECK_DF macro
- _CRTDBG_LEAK_CHECK_DF macro
- _CrtDumpMemoryLeaks function
- CRTDBG_CHECK_CRT_DF macro
- _CRTDBG_CHECK_CRT_DF macro
ms.assetid: 71b2eab4-7f55-44e8-a55a-bfea4f32d34c
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 68a187283eedadcd2f435b0900fde648a5010368
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32396967"
---
# <a name="crtdumpmemoryleaks"></a>_CrtDumpMemoryLeaks

メモリ リークが発生したときに、デバッグ ヒープ内のすべてのメモリ ブロックをダンプします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C

int _CrtDumpMemoryLeaks( void );
```

## <a name="return-value"></a>戻り値

**_CrtDumpMemoryLeaks**メモリ リークが見つかった場合は TRUE を返します。 それ以外の場合、関数は FALSE を返します。

## <a name="remarks"></a>コメント

**_CrtDumpMemoryLeaks**関数では、プログラムの実行が開始されて以来、メモリ リークが発生するかどうかを判断します。 メモリ リークが見つかると、ヒープ内のすべてのオブジェクトのデバッグ ヘッダー情報が、ユーザーが判読できる形式でダンプされます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていないへの呼び出し **_CrtDumpMemoryLeaks**プリプロセス時に削除されます。

**_CrtDumpMemoryLeaks**は頻繁に、アプリケーションによって割り当てられたすべてのメモリが解放されたことを確認する、プログラム実行の終了時に呼び出されます。 関数は、呼び出すことができますに自動的にプログラムの終了を有効にして、 **_CRTDBG_LEAK_CHECK_DF**のビット フィールド、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグを使用して、 [_CrtSetDbgFlag](crtsetdbgflag.md)関数。

**_CrtDumpMemoryLeaks**呼び出し[_CrtMemCheckpoint](crtmemcheckpoint.md)をヒープの現在の状態を取得し、解放されていないブロックの状態をスキャンします。 解放されたブロックが発生したときに **_CrtDumpMemoryLeaks**呼び出し[_CrtMemDumpAllObjectsSince](crtmemdumpallobjectssince.md)プログラム実行の開始からヒープに割り当てられたすべてのオブジェクトの情報をダンプします。

既定では、内部 C ランタイム ブロック (**_CRT_BLOCK**) メモリ ダンプ操作には含まれません。 [_CrtSetDbgFlag](crtsetdbgflag.md)を有効にする関数を使用することができます、 **_CRTDBG_CHECK_CRT_DF**ビットの **_crtDbgFlag**にこれらのブロックをリーク検出プロセスに含めます。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「[ヒープ状態をレポートする関数](/visualstudio/debugger/crt-debug-heap-details)です。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_CrtDumpMemoryLeaks**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法のサンプルについては **_CrtDumpMemoryLeaks**を参照してください[crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)です。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
