---
title: _cwait | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- cwait function
- _cwait function
ms.assetid: d9b596b5-45f4-4e03-9896-3f383cb922b8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 878c1c08dabe52a31a2bdf377c3e0bb167a9ae5d
ms.sourcegitcommit: 6e3cf8df676d59119ce88bf5321d063cf479108c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2018
ms.locfileid: "34450949"
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
指定されたプロセスの結果コードを格納するバッファーへのポインターまたは**NULL**です。

*procHandle*<br/>
待機するプロセスを識別するハンドル (前に終了する必要のあるプロセスは、 **_cwait**返すことができます)。

*action*<br/>
Windows オペレーティング システムのアプリケーションです。 NULL: は無視されます。その他のアプリケーション: を実行するアクション コード*procHandle*です。

## <a name="return-value"></a>戻り値

指定されたプロセスが正常に完了すると、指定されたプロセスのハンドルを返し、設定*返し、termstat*指定されたプロセスによって返される結果のコードにします。 それ以外の場合、-1 を返し、設定**errno**次のようにします。

|[値]|説明|
|-----------|-----------------|
|**ECHILD**|指定されたプロセスが存在しない*procHandle*が無効かへの呼び出し、 [GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)または[WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx) API が失敗しました。|
|**EINVAL**|*アクション*が無効です。|

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Cwait**関数によって提供される、指定されたプロセスのプロセス ID の終了を待機*procHandle*です。 値*procHandle*に渡される **_cwait**への呼び出しによって返される値にする必要があります、 [_spawn](../../c-runtime-library/spawn-wspawn-functions.md)関数を指定されたプロセスを作成します。 前にプロセス ID が終了した場合 **_cwait**が呼び出されると、 **_cwait**が直ちに返されます。 **_cwait**すべてのプロセスでその他の既知のプロセスを待機するために使用する有効なハンドル (*procHandle*) が存在します。

*返し、termstat*指定されたプロセスのリターン コードを格納するバッファーを指します。 値*返し、termstat* 、Windows を呼び出すことによって、指定されたプロセスが正常に終了しているかどうかを示す[ExitProcess](http://msdn.microsoft.com/library/windows/desktop/ms682658.aspx) API です。 **ExitProcess**が、指定されたプロセスを呼び出した場合、内部的に呼び出されます**終了**または **_exit**から返します**メイン**、やの末尾に達した**メイン**. を通じて渡される値の詳細については*返し、termstat*を参照してください[GetExitCodeProcess](http://msdn.microsoft.com/library/windows/desktop/ms683189.aspx)です。 場合 **_cwait**を使用して呼び出す、 **NULL**値*返し、termstat*、指定されたプロセスのリターン コードは格納されません。

*アクション*の親子関係は、これらの環境で実装されていないため、Windows オペレーティング システムによってパラメーターが無視されます。

しない限り、 *procHandle*が-1 または-2 (現在のプロセスまたはスレッドへのハンドル) のハンドルは閉じられます。 したがって、この状況では、返されたハンドルは使用しないでください。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
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
