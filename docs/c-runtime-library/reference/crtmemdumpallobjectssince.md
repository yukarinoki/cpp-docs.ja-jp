---
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
apiname:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: 7de0ee9ff166af6336a8d14aa0dbd07dbd7d23fc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62347458"
---
# <a name="crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

プログラムの実行開始時以降または指定されたヒープ状態以降のヒープ内のオブジェクトについての情報をダンプします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>パラメーター

*state*<br/>
ダンプの開始点となるヒープ状態へのポインターまたは **NULL**。

## <a name="remarks"></a>Remarks

**_CrtMemDumpAllObjectsSince**関数は、ユーザーが判読できる形式でヒープに割り当てられたオブジェクトのデバッグ ヘッダー情報をダンプします。 ダンプ情報は、割り当ての追跡とメモリの問題の検出のためにアプリケーションで使用できます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtMemDumpAllObjectsSince**プリプロセス時に削除されます。

**_CrtMemDumpAllObjectsSince**の値を使用して、*状態*ダンプ操作を開始する場所を特定するパラメーター。 指定したヒープ状態からダンプを開始する、*状態*パラメーターはへのポインターである必要があります、 **_CrtMemState**構造内で塗りつぶされて[_CrtMemCheckpoint](crtmemcheckpoint.md)する前に **_CrtMemDumpAllObjectsSince**が呼び出されました。 ときに*状態*は**NULL**関数は、プログラムの実行開始からダンプを開始します。

アプリケーションが呼び出してダンプ フック関数をインストールした場合[_CrtSetDumpClient](crtsetdumpclient.md)、たび **_CrtMemDumpAllObjectsSince**についての情報をダンプする **_CLIENT_BLOCK**型のブロック、アプリケーションによって提供されたダンプ関数も呼び出します。 既定では、内部 C ランタイム ブロック (**_CRT_BLOCK**) メモリ ダンプ操作には含まれません。 [_CrtSetDbgFlag](crtsetdbgflag.md)を有効にする関数を使用できます、 **_CRTDBG_CHECK_CRT_DF**のビット **_crtDbgFlag**これらのブロックを含めるようにします。 また、解放済みまたは無視としてマークされているブロック (**_FREE_BLOCK**、**_IGNORE_BLOCK**) は、メモリ ダンプに含まれません。

ヒープ状態関数の詳細については、 **_CrtMemState**構造体は、「 [Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 デバッグ バージョンのベース ヒープでのメモリ ブロックの割り当て、初期化、管理の方法について詳しくは、「 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)」をご覧ください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法の例については **_CrtMemDumpAllObjectsSince**を参照してください[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)します。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
