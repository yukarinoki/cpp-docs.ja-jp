---
title: _CrtMemDifference
ms.date: 11/04/2016
apiname:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.assetid: 0f327278-b551-482f-958b-76941f796ba4
ms.openlocfilehash: f2c6306bf604737d0ace142674b21845a08e2dee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339469"
---
# <a name="crtmemdifference"></a>_CrtMemDifference

2 つのメモリ状態を比較し、その違いを返します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
int _CrtMemDifference(
   _CrtMemState *stateDiff,
   const _CrtMemState *oldState,
   const _CrtMemState *newState
);
```

### <a name="parameters"></a>パラメーター

*stateDiff*<br/>
ポインターを **_CrtMemState** (返される) の 2 つのメモリ状態の違いを格納するために使用する構造体。

*oldState*<br/>
以前のメモリ状態へのポインター (**_CrtMemState**構造)。

*newState*<br/>
以降のメモリ状態へのポインター (**_CrtMemState**構造)。

## <a name="return-value"></a>戻り値

メモリの状態が大きく異なる場合 **_CrtMemDifference** TRUE を返します。 それ以外の場合、関数は FALSE を返します。

## <a name="remarks"></a>Remarks

**_CrtMemDifference**関数の比較*oldState*と*newState*し、その違いを*stateDiff*、しすることができますメモリ リークおよびその他のメモリの問題を検出するために、アプリケーションで使用されます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtMemDifference**プリプロセス時に削除されます。

*newState*と*oldState*それぞれ有効なポインターである必要があります、 **_CrtMemState**での入力が完了するには、Crtdbg.h で定義されている構造[_CrtMemCheckpoint](crtmemcheckpoint.md)呼び出す前に **_CrtMemDifference**します。 *stateDiff*の以前に割り当てられたインスタンスへのポインターである必要があります、 **_CrtMemState**構造体。 場合*stateDiff*、 *newState*、または*oldState*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 続けるには、実行が許可された場合[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)に設定されている**EINVAL**関数は FALSE を返します。

**_CrtMemDifference**比較、 **_CrtMemState**フィールド値内のブロックの*oldState*に*newState* に結果を格納および*stateDiff*します。 割り当てられているブロックの型の数または各型に割り当てられているブロックの合計数が 2 つのメモリ状態で異なる場合、この 2 つの状態は、大きく異なると言えます。 一度に割り当てられた 2 つの状態と割り当ての合計の差の 2 つの状態が格納されたもの量の最大値の差*stateDiff*します。

既定では、内部 C ランタイム ブロック (**_CRT_BLOCK**) メモリ状態操作には含まれません。 [_CrtSetDbgFlag](crtsetdbgflag.md)を有効にする関数を使用できます、 **_CRTDBG_CHECK_CRT_DF**のビット **_crtDbgFlag**リークの検出とその他のメモリ状態にこれらのブロックを含める操作です。 解放されたメモリ ブロック (**_FREE_BLOCK**) が発生しない **_CrtMemDifference**に TRUE を返します。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_CrtMemDifference**|\<crtdbg.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

**ライブラリ:** デバッグ バージョン[CRT ライブラリの機能](../../c-runtime-library/crt-library-features.md)のみです。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
