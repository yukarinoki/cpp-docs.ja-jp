---
title: _CrtMemDifference
description: '詳細については、次を参照してください: _CrtMemDifference'
ms.date: 3/8/2021
api_name:
- _CrtMemDifference
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
- _CrtMemDifference
- CrtMemDifference
helpviewer_keywords:
- CrtMemDifference function
- _CrtMemDifference function
ms.openlocfilehash: 9a6a213df867f98bfb921abd940ba23297c5ffef
ms.sourcegitcommit: 90c300b74f6556cb5d989802d2e80d79542f55e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/09/2021
ms.locfileid: "102514604"
---
# `_CrtMemDifference`

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

*`stateDiff`*\
**`_CrtMemState`** 2 つのメモリ状態 (返される) の相違点を格納するために使用される構造体へのポインター。

*`oldState`*\
以前のメモリ状態 ( **`_CrtMemState`** 構造体) へのポインター。

*`newState`*\
後のメモリ状態 ( **`_CrtMemState`** 構造体) へのポインター。

## <a name="return-value"></a>戻り値

メモリ状態が大きく異なる場合、は **`_CrtMemDifference`** を返し `TRUE` ます。 それ以外の場合、関数は FALSE を返します。

## <a name="remarks"></a>注釈

関数はとを比較し、 **`_CrtMemDifference`** それらの *`oldState`* 違いを *`newState`* に格納し *`stateDiff`* ます。これをアプリで使用して、メモリリークなどのメモリの問題を検出できます。 [_DEBUG](../../c-runtime-library/debug.md)が定義されていない場合、の呼び出し **`_CrtMemDifference`** はプリプロセス中に削除されます。

*`newState`* とは、を *`oldState`* **`_CrtMemState`** 呼び出す前にによって設定された、crtdbg.h で定義されている構造体への有効なポインターである必要があり [`_CrtMemCheckpoint`](crtmemcheckpoint.md) **`_CrtMemDifference`** ます。 *`stateDiff`* は、以前に割り当てられた構造体のインスタンスへのポインターである必要があり **`_CrtMemState`** ます。 、、またはがの場合は、「 *`stateDiff`* *`newState`* *`oldState`* **`NULL`** [パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーターハンドラーが呼び出されます。 実行の継続が許可された場合、 [`errno, _doserrno, _sys_errlist, and _sys_nerr`](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) がに設定され、 **`EINVAL`** 関数から FALSE が返されます。

**`_CrtMemDifference`** の **`_CrtMemState`** ブロックのフィールド値とのブロックのフィールド値 *`oldState`* を比較し、 *`newState`* 結果をに格納し *`stateDiff`* ます。 割り当てられているブロックの型の数または各型に割り当てられているブロックの合計数が 2 つのメモリ状態で異なる場合、この 2 つの状態は、大きく異なると言えます。 2つの状態に対して一度に割り当てられた最大量の差と、2つの状態の合計割り当ての差はにも格納され *`stateDiff`* ます。

既定では、内部 C ランタイムブロック () は、 **`_CRT_BLOCK`** メモリ状態操作に含まれていません。 [_CrtSetDbgFlag](crtsetdbgflag.md)関数を使用すると、のビットをオンにして、 **`_CRTDBG_CHECK_CRT_DF`** これらのブロックを **`_crtDbgFlag`** リーク検出などのメモリ状態操作に含めることができます。 解放されたメモリブロック ( **`_FREE_BLOCK`** ) **`_CrtMemDifference`** は、を返しません `TRUE` 。

ヒープ状態関数と構造体の詳細については **`_CrtMemState`** 、「 [ヒープ状態レポート関数](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。 デバッグ バージョンのベース ヒープに対するメモリ ブロックの割り当て、初期化、管理方法については、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**`_CrtMemDifference`**|`<crtdbg.h>`|`<errno.h>`|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

**ライブラリ:**[C ランタイムライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグバージョンのみ。

## <a name="see-also"></a>こちらもご覧ください

[デバッグルーチン](../../c-runtime-library/debug-routines.md)\
[`_crtDbgFlag`](../../c-runtime-library/crtdbgflag.md)\
