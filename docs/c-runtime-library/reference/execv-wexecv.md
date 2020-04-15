---
title: _execv、_wexecv
ms.date: 4/2/2020
api_name:
- _wexecv
- _execv
- _o__execv
- _o__wexecv
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
- api-ms-win-crt-process-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _execv
- _wexecv
- wexecv
helpviewer_keywords:
- _wexecv function
- _execv function
- wexecv function
- execv function
ms.assetid: 8dbaf7bc-9040-4316-a0c1-db7e866b52af
ms.openlocfilehash: 638364afa75fa1b04b598370473dee48964c5763
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81347889"
---
# <a name="_execv-_wexecv"></a>_execv、_wexecv

新しい子プロセスを読み込んで実行します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
intptr_t _execv(
   const char *cmdname,
   const char *const *argv
);
intptr_t _wexecv(
   const wchar_t *cmdname,
   const wchar_t *const *argv
);
```

### <a name="parameters"></a>パラメーター

*Cmdname*<br/>
実行するファイルのパス。

*Argv*<br/>
パラメーターへのポインターの配列。

## <a name="return-value"></a>戻り値

成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。 戻り値 -1 はエラーを示し、その場合は**errno**グローバル変数が設定されます。

|**errno**値|説明|
|-------------------|-----------------|
|**E2BIG**|引数と環境設定には、32 KB を超える領域が必要です。|
|**エアッケ**|指定されたファイルでロック違反または共有違反が発生しています。|
|**Einval**|無効なパラメーター。|
|**EMFILE**|開いているファイルの数が多すぎます (指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります)。|
|**エノエント**|ファイルまたはパスが見つかりません。|
|**ENOEXEC**|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|
|**エノメム**|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (呼び出しプロセスが正しく割り当てられていないことを示します)。|

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの各関数は新しいプロセスを読み込んで実行し、コマンド ライン引数へのポインターの配列を渡します。

**_execv**関数は、パラメーターを検証します。 *cmdname*が null ポインターの場合、または*argv*が null ポインターの場合、空の配列へのポインター、または配列に最初の引数として空の文字列が含まれている場合 **、_execv**関数は[、パラメーターの検証](../../c-runtime-library/parameter-validation.md)で説明されているように無効なパラメーター ハンドラーを呼び出します。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、-1 を返します。 プロセスは起動されません。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|機能|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_execv**|\<process.h>|\<errno.h>|
|**_wexecv**|\<process.h> または \<wchar.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="example"></a>例

「[_exec 関数、_wexec 関数](../../c-runtime-library/exec-wexec-functions.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[中止](abort.md)<br/>
[atexit](atexit.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
