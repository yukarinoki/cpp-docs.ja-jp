---
title: system、_wsystem
ms.date: 4/2/2020
api_name:
- system
- _wsystem
- _o__wsystem
- _o_system
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
- api-ms-win-crt-runtime-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tsystem
- _wsystem
helpviewer_keywords:
- _wsystem function
- wsystem function
- tsystem function
- _tsystem function
- system function
- commands, executing
- command interpreter
ms.assetid: 7d3df2b6-f742-49ce-bf52-012b0aee3df5
ms.openlocfilehash: 09353c9cda2bc85d91f57806bc3497e49a19f803
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82912387"
---
# <a name="system-_wsystem"></a>system、_wsystem

コマンドを実行します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int system(
   const char *command
);
int _wsystem(
   const wchar_t *command
);
```

### <a name="parameters"></a>パラメーター

*メニュー*<br/>
実行するコマンド。

## <a name="return-value"></a>戻り値

*Command*が**NULL**でコマンドインタープリターが見つかった場合、は0以外の値を返します。 コマンドインタープリターが見つからない場合、は0を返し、 **errno**を**ENOENT**に設定します。 *Command*が**NULL**でない場合、 **system**はコマンドインタープリターによって返された値を返します。 コマンド インタープリターから値 0 が返された場合にのみ、値 0 を返します。 戻り値-1 はエラーを示し、 **errno**は次のいずれかの値に設定されます。

|||
|-|-|
| **E2BIG** | 引数リスト (システムに依存する) が大きすぎます。 |
| **ENOENT** | コマンド インタープリターが見つかりません。 |
| **ENOEXEC** | 形式が無効なため、コマンド インタープリター ファイルを実行できません。 |
| **ENOMEM** | コマンドを実行するために十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (これは、呼び出しを実行しているプロセスが正しく割り当てられなかったことを示します)。 |

これらのリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>解説

**System**関数は、コマンドインタープリターに*コマンド*を渡します。このコマンドは、オペレーティングシステムコマンドとして文字列を実行します。 **システム**は、 **COMSPEC**および**PATH**環境変数を使用して、コマンドインタープリターファイル cmd.exe を検索します。 *Command*が**NULL**の場合、関数は、コマンドインタープリターが存在するかどうかをチェックします。

**システム**を呼び出す前に、 [fflush](fflush.md)または[_flushall](flushall.md)を使用して明示的にフラッシュするか、ストリームを閉じる必要があります。

**_wsystem**は**システム**のワイド文字バージョンです。**_wsystem**の*コマンド*引数は、ワイド文字列です。 それ以外では、これらの関数の動作は同じです。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**システム**|**システム**|**_wsystem**|

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**システム**|\<process.h> または \<stdlib.h>|
|**_wsystem**|\<process.h> または \<stdlib.h> または \<wchar.h>|

互換性の詳細については、「[互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

この例では、**システム**を使用してテキストファイルを入力します。

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crt_systemtxt"></a>入力: crt_system.txt

```Input
Line one.
Line two.
```

### <a name="output"></a>出力

```Output
Line one.
Line two.
```

## <a name="see-also"></a>関連項目

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
