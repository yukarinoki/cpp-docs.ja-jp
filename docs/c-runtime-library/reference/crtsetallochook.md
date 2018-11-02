---
title: _CrtSetAllocHook
ms.date: 11/04/2016
apiname:
- _CrtSetAllocHook
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
- _CrtSetAllocHook
- CrtSetAllocHook
helpviewer_keywords:
- _CrtSetAllocHook function
- CrtSetAllocHook function
ms.assetid: 405df37b-2fd1-42c8-83bc-90887f17f29d
ms.openlocfilehash: cfa466ec4bce6034c15a627ccab4ee4bb0ef8f5b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533680"
---
# <a name="crtsetallochook"></a>_CrtSetAllocHook

C ランタイム デバッグ メモリ割り当てプロセスにフックして、クライアント定義割り当て関数をインストールします (デバッグ バージョンのみ)。

## <a name="syntax"></a>構文

```C
_CRT_ALLOC_HOOK _CrtSetAllocHook(
   _CRT_ALLOC_HOOK allocHook
);
```

### <a name="parameters"></a>パラメーター

*allocHook*<br/>
C ランタイム デバッグ メモリ割り当てプロセスにフックする新しいクライアント定義割り当て関数。

## <a name="return-value"></a>戻り値

以前に定義された割り当てフック関数を返しますまたは**NULL**場合*allocHook*は**NULL**します。

## <a name="remarks"></a>Remarks

**_CrtSetAllocHook**により、アプリケーションが C ランタイム デバッグ ライブラリのメモリ割り当てプロセスに独自の割り当て関数をフックします。 そのため、メモリ ブロックの割り当て、再割り当て、または解放を行うためのデバッグ割り当て関数へのすべての呼び出しは、アプリケーションのフック関数への呼び出しをトリガーします。 **_CrtSetAllocHook**割り当てパターン、および後での割り当て情報を記録する機会を検証する機能テスト アプリケーションがメモリ不足の状況を処理する方法の簡単な方法でアプリケーションを提供します。分析します。 ときに[_DEBUG](../../c-runtime-library/debug.md)が定義されていない、呼び出し **_CrtSetAllocHook**プリプロセス時に削除されます。

**_CrtSetAllocHook**関数で指定された新しいクライアント定義割り当て関数をインストールする*allocHook*し、以前に定義されたフック関数を返します。 次の例は、クライアント定義割り当てフックをどのようにプロトタイプ宣言するかを示しています。

```C
int YourAllocHook( int allocType, void *userData, size_t size,
                   int blockType, long requestNumber,
                   const unsigned char *filename, int lineNumber);
```

**AllocType**引数が割り当て操作の種類を指定します (**_HOOK_ALLOC**、 **_HOOK_REALLOC**、および **_HOOK_FREE**) します。割り当てのフック関数への呼び出しをトリガーします。 ときにトリガーする割り当ての種類は **_HOOK_FREE**、 *userData*解放されるメモリ ブロックのユーザー データ セクションへのポインターです。 ただし、ときにトリガーする割り当ての種類は **_HOOK_ALLOC**または **_HOOK_REALLOC**、 *userData*は**NULL**メモリ ブロック割り当てられていないまだします。

*サイズ*ブロック メモリのサイズ (バイト単位) で指定*blockType* 、メモリ ブロックの型を示す*requestNumber*メモリ ブロックのオブジェクト割り当て順序番号は、し、場合は、使用可能な*filename*と**lineNumber**がトリガーする割り当て操作が開始されたソース ファイル名と行番号を指定します。

フック関数は処理の完了後、続行方法を主要な C ランタイム割り当てプロセスに伝えるブール値を返す必要があります。 フック関数が、主要な割り当てプロセスが続行としてかどうか、フック関数が呼び出されたことはありません、フック関数が返す必要がありますが場合**TRUE**します。 このようにすると、元のトリガーする割り当て操作が実行されます。 フック関数は、この実装を使用して、現在の割り当て操作またはデバッグ ヒープの状態に影響を与えずに、後で分析するための割り当て情報を収集および保存できます。

フック関数がトリガーする割り当て操作が呼び出されたかどうかと、失敗した、フック関数が返す必要がありますとして続行する主要な割り当てプロセスが場合**FALSE**します。 フック関数は、この実装を使用して、さまざまなメモリの状況とデバッグ ヒープの状態をシミュレートし、各状況をアプリケーションがどのように処理するかをテストできます。

フック関数をクリアするには、渡す**NULL**に **_CrtSetAllocHook**します。

方法の詳細について **_CrtSetAllocHook**他のメモリ管理関数や、独自のクライアント定義フック関数を記述する方法で使用できる[デバッグ用フック関数の作成](/visualstudio/debugger/debug-hook-function-writing)です。

> [!NOTE]
> **_CrtSetAllocHook**でサポートされていません **/clr: 純粋な**します。 **/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 では削除します。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_CrtSetAllocHook**|\<crtdbg.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のデバッグ バージョンのみ。

## <a name="example"></a>例

使用する方法の例については **_CrtSetAllocHook**を参照してください[crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)します。

## <a name="see-also"></a>関連項目

[デバッグ ルーチン](../../c-runtime-library/debug-routines.md)<br/>
[_CrtGetAllocHook](crtgetallochook.md)<br/>
