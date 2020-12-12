---
description: '詳細については、次を参照してください: _CrtMemCheckpoint'
title: _CrtMemCheckpoint
ms.date: 11/04/2016
api_name:
- _CrtMemCheckpoint
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
- CrtMemCheckpoint
- _CrtMemCheckpoint
- crtdbg/_CrtMemCheckpoint
helpviewer_keywords:
- CrtMemCheckpoint function
- _CrtMemCheckpoint function
ms.assetid: f1bacbaa-5a0c-498a-ac7a-b6131d83dfbc
ms.openlocfilehash: f7a88e63c99c063999f3de0d01e019fecd10496f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319678"
---
# <a name="_crtmemcheckpoint"></a>_CrtMemCheckpoint

デバッグヒープの現在の状態を取得し、アプリケーションによって提供される **_CrtMemState** 構造体に格納します (デバッグバージョンのみ)。

## <a name="syntax"></a>構文

```C
void _CrtMemCheckpoint(
   _CrtMemState *state
);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
メモリチェックポイントを格納する **_CrtMemState** 構造体へのポインター。

## <a name="remarks"></a>解説

**_CrtMemCheckpoint** 関数は、特定の時点におけるデバッグヒープの現在の状態のスナップショットを作成します。 [_CrtMemDifference](crtmemdifference.md) などの他のヒープ状態関数は、このスナップショットを使用してメモリ リークおよびその他の問題を検出できます。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、 **_CrtMemState** の呼び出しはプリプロセス中に削除されます。

アプリケーションは、Crtdbg.h で定義されている、以前に割り当てられた **_CrtMemState** 構造体のインスタンスへのポインターを *state* パラメーターに渡す必要があります。 チェックポイントの作成中にエラーが発生し **_CrtMemCheckpoint** 場合は、問題を説明する **_CRT_WARN** デバッグレポートを生成します。

ヒープ状態関数と **_CrtMemState** 構造体の詳細については、「 [ヒープ状態レポート関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

*State* が **NULL** の場合、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 [errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) は **EINVAL** に設定され、関数はを返します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtMemCheckpoint**|\<crtdbg.h>, \<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

**ライブラリ:** UCRT のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtMemDifference](crtmemdifference.md)<br/>
