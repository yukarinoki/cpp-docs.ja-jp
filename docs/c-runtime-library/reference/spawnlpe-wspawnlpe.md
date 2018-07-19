---
title: _spawnlpe、_wspawnlpe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _spawnlpe
- _wspawnlpe
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
- spawnlpe
- _wspawnlpe
- _spawnlpe
- wspawnlpe
dev_langs:
- C++
helpviewer_keywords:
- _wspawnlpe function
- wspawnlpe function
- processes, creating
- spawnlpe function
- _spawnlpe function
- processes, executing new
- process creation
ms.assetid: e171ebfa-70e7-4c44-8331-2a291fc17bd6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: be8e86ddb6405c39f877bd9065a931b66238c2b6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413308"
---
# <a name="spawnlpe-wspawnlpe"></a>_spawnlpe、_wspawnlpe

新しいプロセスを作成して実行します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
intptr_t _spawnlpe(
   int mode,
   const char *cmdname,
   const char *arg0,
   const char *arg1,
   ... const char *argn,
   NULL,
   const char *const *envp
);
intptr_t _wspawnlpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *arg0,
   const wchar_t *arg1,
   ... const wchar_t *argn,
   NULL,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
呼び出しプロセスの実行モード。

*cmdname*<br/>
実行されるファイルのパス。

*arg0*、 *arg1*、.*argn*<br/>
引数へのポインターのリスト。 *Arg0*引数がへのポインターでは通常*cmdname*です。 引数*arg1*を通じて*argn*新しい引数リストを形成する文字列へのポインターです。 次の*argn*、存在する必要があります、 **NULL**引数リストの末尾を示すへのポインター。

*envp*<br/>
環境設定へのポインターの配列。

## <a name="return-value"></a>戻り値

同期からの戻り値 **_spawnlpe**または **_wspawnlpe** (**_P_WAIT**向けに指定された*モード*)、new の終了ステータスですプロセスです。 非同期の戻り値 **_spawnlpe**または **_wspawnlpe** (**_P_NOWAIT**または **_P_NOWAITO**向けに指定された*モード*) がプロセス ハンドルです。 プロセスが正常に終了した場合、終了ステータスは 0 です。 具体的には、生成されたプロセスを呼び出す 0 以外の引数を使用する場合に、終了ステータスを 0 以外の値に設定できます、**終了**ルーチンです。 新しいプロセスが明示的に終了ステータスを正の値に設定しなかった場合、正の値の終了ステータスは中止または割り込みによる異常終了を示します。 戻り値-1 は、(新しいプロセスは開始されません) エラーを示します。 この場合、 **errno**は、次の値のいずれかに設定します。

|||
|-|-|
**E2BIG**|引数リストが 1024 バイトを超えています。
**EINVAL**|*モード*引数が無効です。
**ENOENT**|ファイルまたはパスが見つかりません。
**ENOEXEC**|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。
**ENOMEM**|新しいプロセスを実行するのに十分なメモリがありません。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

これらの各関数は、新しいプロセスを作成して実行し、各コマンド ライン引数を個別のパラメーターとして渡し、環境設定へのポインターの配列を渡します。 これらの関数を使用して、**パス**環境変数を実行するファイルを検索します。

これらの関数では、パラメーターの検証が行われます。 いずれか*cmdname*または*arg0*空の文字列または null ポインターの場合、無効なパラメーター ハンドラーが呼び出され、」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**、し、-1 を返します。 新しいプロセスは起動されません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_spawnlpe**|\<process.h>|
|**_wspawnlpe**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)」の使用例を参照してください。

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
