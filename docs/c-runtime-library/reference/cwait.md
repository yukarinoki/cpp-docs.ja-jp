---
title: _cwait
ms.date: 4/2/2020
api_name:
- _cwait
- _o__cwait
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _cwait
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
ms.openlocfilehash: 9e2e23acb041004b9e96d1c6558ae195ed522155
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914797"
---
# <a name="_cwait"></a>_cwait

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

*termstat*<br/>
指定されたプロセスの結果コードが格納されるバッファーへのポインター、または**NULL**。

*procHandle*<br/>
待機するプロセス (つまり、 **_cwait**が返される前に終了する必要があるプロセス) へのハンドル。

*action*<br/>
NULL: Windows オペレーティングシステムアプリケーションでは無視されます。他のアプリケーションの場合: *procHandle*で実行するアクションコード。

## <a name="return-value"></a>戻り値

指定されたプロセスが正常に完了すると、は指定されたプロセスのハンドルを返し、 *termstat*を指定されたプロセスによって返される結果コードに設定します。 それ以外の場合、は-1 を返し、 **errno**を次のように設定します。

|値|説明|
|-----------|-----------------|
|**ECHILD**|指定されたプロセスが存在しないか、 *procHandle*が無効であるか、 [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)または[WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject) API の呼び出しが失敗しました。|
|**EINVAL**|*アクション*が無効です。|

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>解説

**_Cwait**関数は、 *procHandle*によって提供される、指定されたプロセスのプロセス ID が終了するまで待機します。 **_Cwait**に渡される*procHandle*の値は、指定されたプロセスを作成した[_spawn](../../c-runtime-library/spawn-wspawn-functions.md)関数の呼び出しによって返される値である必要があります。 **_Cwait**が呼び出される前にプロセス ID が終了した場合、 **_cwait**は直ちに返されます。 **_cwait**は、任意のプロセスが、有効なハンドル (*procHandle*) が存在する他の既知のプロセスを待機するために使用できます。

*termstat*は、指定されたプロセスのリターンコードが格納されるバッファーを指します。 *Termstat*の値は、指定されたプロセスが Windows [ExitProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitprocess) API を呼び出すことによって正常に終了したかどうかを示します。 **ExitProcess**は、指定されたプロセスが**exit**または **_exit**を呼び出した場合、 **main**からを返した場合、または**main**の最後に到達した場合に、内部的に呼び出されます。 *Termstat*で返される値の詳細については、「 [GetExitCodeProcess](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodeprocess)」を参照してください。 *Termstat*に**NULL**値を使用して **_cwait**を呼び出すと、指定されたプロセスのリターンコードは格納されません。

Windows オペレーティングシステムでは、このような環境に親子関係が実装されていないため、*アクション*パラメーターは無視されます。

*ProcHandle*が-1 または-2 (現在のプロセスまたはスレッドへのハンドル) でない限り、ハンドルは閉じられます。 したがって、この状況では、返されたハンドルは使用しないでください。

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_cwait**|\<process.h>|\<errno.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

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

[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
