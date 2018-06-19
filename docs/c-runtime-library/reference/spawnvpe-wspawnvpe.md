---
title: _spawnvpe、_wspawnvpe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _spawnvpe
- _wspawnvpe
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
- _spawnvpe
- wspawnvpe
- spawnvpe
- _wspawnvpe
dev_langs:
- C++
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55016fcc346e5894f5fd3ffe4a8e9a2f43b5ab87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32413558"
---
# <a name="spawnvpe-wspawnvpe"></a>_spawnvpe、_wspawnvpe

新しいプロセスを作成して実行します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
intptr_t _spawnvpe(
   int mode,
   const char *cmdname,
   const char *const *argv,
   const char *const *envp
);
intptr_t _wspawnvpe(
   int mode,
   const wchar_t *cmdname,
   const wchar_t *const *argv,
   const wchar_t *const *envp
);
```

### <a name="parameters"></a>パラメーター

*モード*<br/>
呼び出しプロセスの実行モード

*cmdname*<br/>
実行されるファイルのパス

*argv*<br/>
引数へのポインターの配列。 引数*argv*[0] は、通常パスへのポインター リアル モードまたはプログラム名への保護モードと*argv*[1] から*argv***[n]**、新しい引数リストを形成する文字列へのポインターです。 引数*argv*[**n** +1] があります、 **NULL**引数リストの末尾を示すへのポインター。

*envp*<br/>
環境設定へのポインターの配列

## <a name="return-value"></a>戻り値

同期からの戻り値 **_spawnvpe**または **_wspawnvpe** (**_P_WAIT**向けに指定された*モード*)、new の終了ステータスですプロセスです。 非同期の戻り値 **_spawnvpe**または **_wspawnvpe** (**_P_NOWAIT**または **_P_NOWAITO**向けに指定された*モード*) がプロセス ハンドルです。 プロセスが正常に終了した場合、終了ステータスは 0 です。 起動されたプロセスが明示的に呼び出す場合、0 以外の値を終了ステータスを設定することができます、**終了**0 以外の引数を持つルーチンです。 新しいプロセスが明示的に終了ステータスを正の値に設定しなかった場合、正の値の終了ステータスは中止または割り込みによる異常終了を示します。 戻り値-1 は、(新しいプロセスは開始されません) エラーを示します。 この場合、 **errno**は、次の値のいずれかに設定します。

|||
|-|-|
**E2BIG**|引数リストが 1024 バイトを超えています。
**EINVAL**|*モード*引数が無効です。
**ENOENT**|ファイルまたはパスが見つかりません。
**ENOEXEC**|指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。
**ENOMEM**|新しいプロセスを実行するのに十分なメモリがありません。

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>コメント

これらの関数は、新しいプロセスを作成して実行し、コマンド ライン引数へポインターの配列を、および環境の設定へポインターの配列を渡します。 これらの関数を使用して、**パス**環境変数を実行するファイルを検索します。

これらの関数では、パラメーターの検証が行われます。 いずれか*cmdname*または*argv* null ポインターでは、場合*argv* null のポインターを指しているまたは*argv*[0] は、空の文字列は、無効ですパラメーター ハンドラーが呼び出されます」の説明に従って[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**、し、-1 を返します。 新しいプロセスは起動されません。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h> または \<process.h>|
|**_wspawnvpe**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

「 [_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)」の使用例を参照してください。

## <a name="see-also"></a>関連項目

[abort](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
