---
title: _cwait
ms.date: 11/04/2016
apiname:
- _cwait
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
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: f7a49497ac71ec15261e1215bd2bbed2e49f42ab
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50489623"
---
# <a name="cwait"></a>_cwait

ほかのプロセスが終了するまで待機します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
intptr_t _cwait(
   int *termstat,
   intptr_t procHandle,
   int action
);
```

### <a name="parameters"></a>パラメーター

*返し、termstat*<br/>
指定されたプロセスの結果コードを格納するバッファーへのポインターまたは**NULL**します。

*procHandle*<br/>
待機するプロセスを識別するハンドル (前に終了する必要のあるプロセスは、 **_cwait**返すことができます)。

*action*<br/>
Windows オペレーティング システムのアプリケーションでは NULL。 無視されますその他のアプリケーション: を実行するアクション コード*procHandle*します。

## <a name="return-value"></a>戻り値

指定されたプロセスのハンドルを返し、設定の指定されたプロセスが正常に完了したら、*返し、termstat*を指定されたプロセスによって返される結果コード。 それ以外の場合、-1 を返し、設定**errno**次のようにします。

|[値]|説明|
|-----------|-----------------|
|**ECHILD**|指定されたプロセスが存在しない*procHandle*が無効かを呼び出し、 [GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)または[WaitForSingleObject](/windows/desktop/api/synchapi/nf-synchapi-waitforsingleobject) API が失敗しました。|
|**EINVAL**|*アクション*が無効です。|

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

**_Cwait**関数によって提供される、指定されたプロセスのプロセス ID の終了を待機*procHandle*します。 値*procHandle*に渡される **_cwait**への呼び出しによって返される値である必要があります、 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md)関数、指定されたプロセスを作成します。 プロセス ID が前に終了した場合は **_cwait**が呼び出され、 **_cwait**が直ちに返されます。 **_cwait**他の任意の既知のプロセスを待機する任意のプロセスで使用できる有効なハンドル (*procHandle*) が存在します。

*返し、termstat*指定されたプロセスのリターン コードを格納するバッファーを指します。 値*返し、termstat* 、Windows を呼び出すことによって、指定されたプロセスが正常に終了しているかどうかを示す[ExitProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-exitprocess) API。 **ExitProcess** 、指定されたプロセスを呼び出す場合、内部的に呼び出されます**終了**または **_exit**から返します**メイン**、やの末尾に達した**メイン**. 経由で返される値の詳細については*返し、termstat*を参照してください[GetExitCodeProcess](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)します。 場合 **_cwait**を呼び出すとき、 **NULL**値*返し、termstat*、指定されたプロセスのリターン コードは格納されません。

*アクション*親子関係がこれらの環境で実装されていないため、Windows オペレーティング システムによってパラメーターは無視されます。

しない限り、 *procHandle*が-1 または-2 (現在のプロセスまたはスレッドへのハンドル) のハンドルは閉じられます。 したがって、この状況では、返されたハンドルは使用しないでください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

```C
// crt_cwait.c
// compile with: /c
// This program launches several processes and waits
// for a specified process to finish.

#define _CRT_RAND_S

#include <windows.h>
#include <process.h>
#include <stdlib.h>
#include <stdio.h>
#include <time.h>

// Macro to get a random integer within a specified range
#define getrandom( min, max ) (( (rand_s (&number), number) % (int)((( max ) + 1 ) - ( min ))) + ( min ))

struct PROCESS
{
   int     nPid;
   char    name[40];
} process[4] = { { 0, "Ann" }, { 0, "Beth" }, { 0, "Carl" }, { 0, "Dave" } };

int main( int argc, char *argv[] )
{
   int termstat, c;
   unsigned int number;

   srand( (unsigned)time( NULL ) );    // Seed randomizer

   // If no arguments, this is the calling process
   if ( argc == 1 )
   {
      // Spawn processes in numeric order
      for ( c = 0; c < 4; c++ ) {
         _flushall();
         process[c].nPid = _spawnl( _P_NOWAIT, argv[0], argv[0],
                                    process[c].name, NULL );
      }

      // Wait for randomly specified process, and respond when done
      c = getrandom( 0, 3 );
      printf( "Come here, %s.\n", process[c].name );
      _cwait( &termstat, process[c].nPid, _WAIT_CHILD );
      printf( "Thank you, %s.\n", process[c].name );

   }
   // If there are arguments, this must be a spawned process
   else
   {
      // Delay for a period that's determined by process number
      Sleep( (argv[1][0] - 'A' + 1) * 1000L );
      printf( "Hi, Dad. It's %s.\n", argv[1] );
   }
}
```

```Output
Hi, Dad. It's Ann.
Come here, Ann.
Thank you, Ann.
Hi, Dad. It's Beth.
Hi, Dad. It's Carl.
Hi, Dad. It's Dave.
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
