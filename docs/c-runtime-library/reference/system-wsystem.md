---
title: system、_wsystem
ms.date: 11/04/2016
apiname:
- system
- _wsystem
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
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
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
ms.openlocfilehash: 46c4949fcc8cfbe4a3477e66b57d8fc6fc97ed73
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62259093"
---
# <a name="system-wsystem"></a>system、_wsystem

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

*command*<br/>
実行するコマンド。

## <a name="return-value"></a>戻り値

場合*コマンド*は**NULL**コマンド インタープリターが見つかると、0 以外の値を返します。 コマンド インタープリターが見つからない場合は 0 を設定**errno**に**ENOENT**します。 場合*コマンド*ない**NULL**、**システム**コマンド インタープリターから返される値を返します。 コマンド インタープリターから値 0 が返された場合にのみ、値 0 を返します。 戻り値 1 のエラーを示すと**errno**値は次のいずれかに設定されます。

|||
|-|-|
| **E2BIG** | 引数リスト (システムに依存する) が大きすぎます。 |
| **ENOENT** | コマンド インタープリターが見つかりません。 |
| **ENOEXEC** | 形式が無効なため、コマンド インタープリター ファイルを実行できません。 |
| **ENOMEM** | コマンドを実行するために十分なメモリがないか、使用できるメモリが破損しているか、または無効なブロックが存在します (これは、呼び出しを実行しているプロセスが正しく割り当てられなかったことを示します)。 |

これらのリターン コードの詳細については、「[_doserrno、errno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」をご覧ください。

## <a name="remarks"></a>Remarks

**システム**関数パス*コマンド*はコマンド インタープリターに文字列として、オペレーティング システムのコマンドを実行します。 **システム**を使用して、 **COMSPEC**と**パス**環境変数の検索コマンド インタープリター ファイル CMD.exe です。 場合*コマンド*は**NULL**関数がだけコマンド インタープリターが存在するかどうかを確認します。

使用して、フラッシュ明示的に[fflush](fflush.md)または[_flushall](flushall.md)を呼び出す前に、任意のストリームを閉じる**システム**します。

**_wsystem**のワイド文字バージョンです**システム**、*コマンド*引数 **_wsystem**はワイド文字列です。 それ以外では、これらの関数の動作は同じです。

### <a name="generic-text-routine-mappings"></a>汎用テキスト ルーチンのマップ

|TCHAR.H のルーチン|_UNICODE および _MBCS が未定義の場合|_MBCS が定義されている場合|_UNICODE が定義されている場合|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tsystem**|**system**|**system**|**_wsystem**|

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**system**|\<process.h> または \<stdlib.h>|
|**_wsystem**|\<process.h> または \<stdlib.h> または \<wchar.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

この例では**システム**をテキスト ファイルを入力します。

```C
// crt_system.c

#include <process.h>

int main( void )
{
   system( "type crt_system.txt" );
}
```

### <a name="input-crtsystemtxt"></a>入力: crt_system.txt

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

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_flushall](flushall.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
