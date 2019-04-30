---
title: _CrtCheckMemory
ms.date: 11/04/2016
apiname:
- _CrtCheckMemory
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
- CrtCheckMemory
- _CrtCheckMemory
helpviewer_keywords:
- _CrtCheckMemory function
- CrtCheckMemory function
ms.assetid: 457cc72e-60fd-4177-ab5c-6ae26a420765
ms.openlocfilehash: cb39a76c140934dabdd1269c02aba6018691f917
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62340392"
---
# <a name="crtcheckmemory"></a>_CrtCheckMemory

デバッグ ヒープで割り当てられたメモリ ブロックの整合性を確認します (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C

int _CrtCheckMemory( void );
```

## <a name="return-value"></a>戻り値

成功した場合、 **_CrtCheckMemory**関数が FALSE を返す TRUE。 それ以外を返します。

## <a name="remarks"></a>Remarks

**_CrtCheckMemory**関数は、基になるベース ヒープを確認して、各メモリ ブロックを調べることによって、デバッグ ヒープ マネージャーによって割り当てられたメモリを検証します。 基になるベース ヒープ、デバッグ ヘッダー情報、または上書きバッファーでは、エラーまたはメモリの不整合が発生した場合 **_CrtCheckMemory**エラー状態を示す情報を含むデバッグ レポートが生成されます。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtCheckMemory**プリプロセス時に削除されます。

動作 **_CrtCheckMemory**のビット フィールドを設定して制御することができます、 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)フラグを使用して、 [_CrtSetDbgFlag](crtsetdbgflag.md)関数。 すると、 **_CRTDBG_CHECK_ALWAYS_DF**ビット フィールドを ON **_CrtCheckMemory**メモリ割り当て操作が要求されるたびに呼び出されます。 この方法は実行速度を低下させますが、エラーをすばやく見つけるために役立ちます。 すると、 **_CRTDBG_ALLOC_MEM_DF**ビット フィールドを OFF と **_CrtCheckMemory**をヒープを確認し、すぐに完了しない**TRUE**します。

この関数は **TRUE** または **FALSE** を返すため、[_ASSERT](assert-asserte-assert-expr-macros.md) 系マクロに渡すことによって、デバッグ用の単純なエラー処理機構を作成できます。 次の例は、ヒープの破損が検出された場合に、アサーション エラーを発生させます。

```C
_ASSERTE( _CrtCheckMemory( ) );
```

詳細について **_CrtCheckMemory**他のデバッグ関数と共に使用することができますを参照してください[Heap State Reporting Functions](/visualstudio/debugger/crt-debug-heap-details)します。 メモリ管理とデバッグ ヒープの概要については、「[CRT デバッグ ヒープ](/visualstudio/debugger/crt-debug-heap-details)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtCheckMemory**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法の例については **_CrtCheckMemory**を参照してください[crt_dbg1](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg1)します。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)<br/>
[_CrtSetDbgFlag](crtsetdbgflag.md)<br/>
