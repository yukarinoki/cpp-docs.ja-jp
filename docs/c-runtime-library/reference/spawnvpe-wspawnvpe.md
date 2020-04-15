---
title: _spawnvpe、_wspawnvpe
ms.date: 4/2/2020
api_name:
- _spawnvpe
- _wspawnvpe
- _o__spawnvpe
- _o__wspawnvpe
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
- _spawnvpe
- wspawnvpe
- _wspawnvpe
helpviewer_keywords:
- _wspawnvpe function
- processes, creating
- _spawnvpe function
- processes, executing new
- wspawnvpe function
- process creation
- spawnvpe function
ms.assetid: 3db6394e-a955-4837-97a1-fab1db1e6092
ms.openlocfilehash: c8a97e99711a2053a26ae850c09c82a4342cda3a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355710"
---
# <a name="_spawnvpe-_wspawnvpe"></a>_spawnvpe、_wspawnvpe

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

*Cmdname*<br/>
実行されるファイルのパス

*Argv*<br/>
引数へのポインターの配列。 引数*argv*[0] は、通常、リアル モードのパスまたはプロテクト モードのプログラム名へのポインタであり *、argv*[1] から*argv*[**n**] は、新しい引数リストを形成する文字列へのポインタです。 引数*argv*[**n** +1] は、引数リストの末尾を示す**NULL**ポインタでなければなりません。

*envp*<br/>
環境設定へのポインターの配列

## <a name="return-value"></a>戻り値

同期 **_spawnvpe**または **_wspawnvpe** ( *mode*に指定 **_P_WAIT** ) からの戻り値は、新しいプロセスの終了ステータスです。 非同期 **_spawnvpe**または **_wspawnvpe** **(mode***に指定*された_P_NOWAITまたは **_P_NOWAITO)** からの戻り値は、プロセス ハンドルです。 プロセスが正常に終了した場合、終了ステータスは 0 です。 生成されたプロセスがゼロ以外の引数を持つ出口ルーチンを明示的に呼び出す場合は **、終了**状況をゼロ以外の値に設定できます。 新しいプロセスが明示的に終了ステータスを正の値に設定しなかった場合、正の値の終了ステータスは中止または割り込みによる異常終了を示します。 戻り値 -1 はエラーを示します (新しいプロセスは開始されません)。 この場合 **、errno**は次のいずれかの値に設定されます。

|||
|-|-|
| **E2BIG** | 引数リストが 1024 バイトを超えています。 |
| **Einval** | *モード*引数が無効です。 |
| **エノエント** | ファイルまたはパスが見つかりません。 |
| **ENOEXEC** | 指定されたファイルが実行可能ファイルでないか、無効な実行可能ファイル形式です。 |
| **エノメム** | 新しいプロセスを実行するのに十分なメモリがありません。 |

リターン コードの詳細については、「[_doserrno、errno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

これらの関数は、新しいプロセスを作成して実行し、コマンド ライン引数へポインターの配列を、および環境の設定へポインターの配列を渡します。 これらの関数は **、PATH**環境変数を使用して、実行するファイルを検索します。

これらの関数では、パラメーターの検証が行われます。 *cmdname*または*argv*のいずれかが null ポインターである場合、または*argv*が null ポインターを指している場合、または*argv*[0] が空の文字列である場合は、「[パラメーターの検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメーター ハンドラーが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、-1 を返します。 新しいプロセスは起動されません。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_spawnvpe**|\<stdio.h> または \<process.h>|
|**_wspawnvpe**|\<stdio.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

[_spawn, _wspawn Functions](../../c-runtime-library/spawn-wspawn-functions.md)の例を参照してください。

## <a name="see-also"></a>関連項目

[中止](abort.md)<br/>
[atexit](atexit.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_onexit、_onexit_m](onexit-onexit-m.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[system、_wsystem](system-wsystem.md)<br/>
