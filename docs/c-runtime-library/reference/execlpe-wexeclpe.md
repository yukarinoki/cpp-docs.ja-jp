---
title: _execlpe、_wexeclpe
ms.date: 11/04/2016
apiname:
- _execlpe
- _wexeclpe
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
- api-ms-win-crt-process-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wexeclpe
- execlpe
- wexeclpe
- _execlpe
helpviewer_keywords:
- wexeclpe function
- _wexeclpe function
- _execlpe function
- execlpe function
ms.assetid: 07b861da-3e7e-4f1d-bb80-ad69b55e5162
ms.openlocfilehash: e3aa4189d2a384a0092c742909e97c5efc52b5ff
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62339365"
---
# <a name="execlpe-wexeclpe"></a>_execlpe、_wexeclpe

新しい子プロセスを読み込んで実行します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
intptr_t _execlpe(
   const char *cmdname,
   const char *arg0,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wexeclpe(
   const wchar_t *cmdname,
   const wchar_t *arg0,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>パラメーター

*cmdname*<br/>
実行するファイルのパス。

*arg0*、.*argn*<br/>
パラメーターへのポインターのリスト。

*envp*<br/>
環境設定へのポインターの配列。

## <a name="return-value"></a>戻り値

成功した場合、これらの関数が呼び出しプロセスに戻ることはありません。 戻り値-1 を場合エラーを示す、 **errno**グローバル変数を設定します。

|**errno**値|説明|
|-------------------|-----------------|
|**E2BIG**|引数と環境設定には、32 KB を超える領域が必要です。|
|**EACCES**|指定されたファイルでロック違反または共有違反が発生しています。|
|**EINVAL**|無効なパラメーター。|
|**EMFILE**|開いているファイルの数が多すぎます (指定されたファイルは、実行可能ファイルであるかどうかを確認するために開く必要があります)。|
|**ENOENT**|ファイルまたはパスが見つかりません。|
|**ENOEXEC**|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。|
|**ENOMEM**|新しいプロセスを実行するのに十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (呼び出しプロセスが正しく割り当てられていないことを示します)。|

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

これらの関数は、新しいプロセスを読み込んで実行し、各コマンド ライン引数を個別のパラメーターとして渡し、環境設定へのポインターの配列も渡します。 これらの関数を使用して、**パス**環境変数を実行するファイルを検索します。

**_Execlpe**関数は、パラメーターを検証します。 いずれか*cmdname*または*arg0* null ポインターまたは空の文字列では、これらの関数は」の説明に従って、無効なパラメーター ハンドラーを呼び出す[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**し、-1 を返します。 新しいプロセスは開始されません。

## <a name="requirements"></a>必要条件

|関数|必須ヘッダー|オプション ヘッダー|
|--------------|---------------------|---------------------|
|**_execlpe**|\<process.h>|\<errno.h>|
|**_wexeclpe**|\<process.h> または \<wchar.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「[_exec 関数、_wexec 関数](../../c-runtime-library/exec-wexec-functions.md)」の例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
