---
title: _CrtMemDumpStatistics | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _CrtMemDumpStatistics
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
- CrtMemDumpStatistics
- _CrtMemDumpStatistics
dev_langs:
- C++
helpviewer_keywords:
- _CrtMemDumpStatistics function
- CrtMemDumpStatistics function
ms.assetid: 27b9d731-3184-4a2d-b9a7-6566ab28a9fe
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 655d9be75fa031cc2cbebfd65c4634528f410e85
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/07/2018
ms.locfileid: "44110527"
---
# <a name="crtmemdumpstatistics"></a>_CrtMemDumpStatistics

指定されたヒープ状態のデバッグ ヘッダー情報をユーザーが判読できる形式でダンプします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void _CrtMemDumpStatistics(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
ダンプするヒープ状態へのポインター。

## <a name="remarks"></a>Remarks

**_CrtMemDumpStatistics**関数は、ユーザーが判読できる形式で、ヒープの指定された状態のデバッグ ヘッダー情報をダンプします。 ダンプ統計情報は、割り当ての追跡とメモリの問題の検出のためにアプリケーションで使用できます。 メモリ状態には、特定のヒープ状態、または 2 つの状態の相違点を含めることができます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtMemDumpStatistics**プリプロセス時に削除されます。

*状態*パラメーターはへのポインターである必要があります、 **_CrtMemState**構造内で塗りつぶされて[_CrtMemCheckpoint](crtmemcheckpoint.md)かによって返される[_CrtMemDifference](crtmemdifference.md)する前に **_CrtMemDumpStatistics**が呼び出されます。 場合*状態*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合**errno**に設定されている**EINVAL**し、アクションは実行されません。 詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>要件

|ルーチンによって返される値|必須ヘッダー|省略可能なヘッダー|
|-------------|---------------------|----------------------|
|**_CrtMemDumpStatistics**|\<crtdbg.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** [CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
