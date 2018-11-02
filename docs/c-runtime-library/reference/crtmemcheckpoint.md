---
title: _CrtMemCheckpoint
ms.date: 11/04/2016
apiname:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: ee435ba3e9e40795280dee0f97feaad32c8b0fc3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50589518"
---
# <a name="crtmemcheckpoint"></a>_CrtMemCheckpoint

デバッグ ヒープの現在の状態を取得し、アプリケーションが指定した格納 **_CrtMemState**構造 (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
ポインター **_CrtMemState**なメモリのチェックポイントを格納する構造体。

## <a name="remarks"></a>Remarks

**_CrtMemCheckpoint**関数は、特定の時点で、デバッグ ヒープの現在の状態のスナップショットを作成します。 [_CrtMemDifference](crtmemdifference.md) などの他のヒープ状態関数は、このスナップショットを使用してメモリ リークおよびその他の問題を検出できます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtMemState**プリプロセス時に削除されます。

アプリケーションの以前に割り当てられたインスタンスへのポインターを渡す必要があります、 **_CrtMemState**構造では、Crtdbg.h で定義されている、*状態*パラメーター。 場合 **_CrtMemCheckpoint**チェックポイントの作成中にエラーが検出すると、関数は、生成、**前述**問題を説明するレポートをデバッグします。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

場合*状態*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)に設定されている**EINVAL**関数を返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>、\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** UCRT のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
