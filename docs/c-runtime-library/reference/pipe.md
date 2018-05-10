---
title: _pipe | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _pipe
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- pipe
- _pipe
dev_langs:
- C++
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e3e636bc5aac889e3c3a16b856525d4d7268e262
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="pipe"></a>_pipe

読み取りおよび書き込み用のパイプを作成します。

> [!IMPORTANT]
> この API は、Windows ランタイムで実行するアプリケーションでは使用できません。 詳細については、「[ユニバーサル Windows プラットフォーム アプリでサポートされていない CRT 関数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)」を参照してください。

## <a name="syntax"></a>構文

```C
int _pipe(
   int *pfds,
   unsigned int psize,
   int textmode
);
```

### <a name="parameters"></a>パラメーター

*pfds*<br/>
2 つの配列を指すポインター **int**読み取りを保持し、ファイル記述子を作成します。

*psize*<br/>
予約するメモリの量。

*textmode*<br/>
ファイル モード。

## <a name="return-value"></a>戻り値

処理が正常に終了した場合は 0 を返します。 エラーを示す、-1 を返します。 エラーが発生した**errno**がこれらの値のいずれかに設定します。

- **EMFILE**、ファイル記述子をこれ以上が使用できることを示します。

- **ENFILE**、システム ファイル テーブルのオーバーフローを示します。

- **EINVAL**、ことを示しますか配列*pfds* null ポインター、またはに対して無効な値*textmode*が渡されました。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**_Pipe**関数を作成、*パイプ*プログラムが他のプログラムに情報を渡すために使用する人為的な I/O チャネルであります。 パイプは、ファイル ポインター、ファイル記述子、またはその両方を持つファイルに似ており、標準ライブラリの入出力関数を使用して読み取りや書き込みを行うことができます。 ただし、パイプは、特定のファイルまたはデバイスを表しません。 代わりに、プログラム自体のメモリに関係なく、オペレーティング システムによって完全に制御されるメモリの一時的なストレージを表します。

**_pipe**に似ています **_open**に読み取ったり書き込んだりするためのパイプを開き、2 つのファイル記述子を 1 つではなくを返します。 プログラムはパイプの両側を使用するか、または必要としない一方の側のパイプを閉じることができます。 たとえば、Windows のコマンド プロセッサを作成、パイプなどのコマンドを実行時に**プログラム 1** | **PROGRAM2**です。

標準出力記述子**プログラム 1**はパイプの書き込み記述子に添付します。 標準入力記述子**PROGRAM2**はパイプの読み取り記述子に添付します。 これにより、他のプログラムに情報を渡すための一時ファイルを作成する必要がなくなります。

**_Pipe**でパイプに 2 つのファイル記述子を返します、 *pfds*引数。 要素*pfds*[0]、読み取り記述子と要素が含まれています*pfds*[1] は書き込み記述子が含まれています。 パイプのファイル記述子は、他のファイル記述子と同様に使用されます。 (低水準の入力と出力関数**読む (_r)** と **_write**から読み取るし、パイプに書き込むことができます)。パイプの終了条件を検出するには、確認、**読む (_r)** 読み取られたバイト数として 0 を返す要求します。

*Psize*引数は、(バイト単位)、パイプに予約するメモリの量を指定します。 *Textmode*引数は、パイプの変換モードを指定します。 マニフェスト定数 **_O_TEXT**テキストの翻訳と定数を指定 **_O_BINARY**バイナリ変換を指定します。 (テキスト モードとバイナリ モードの詳細については、「[fopen、_wfopen](fopen-wfopen.md)」を参照してください。)場合、 *textmode*引数が 0 の場合、 **_pipe** 、既定のモード変数で指定されている既定の変換モードを使用して[_fmode](../../c-runtime-library/fmode.md)です。

マルチスレッド プログラムでは、ロックは実行されません。 返されるファイル記述子が新しく開き後にするまでの任意のスレッドからは参照できません、 **_pipe**呼び出しが完了します。

使用する、 **_pipe**関数の親プロセスと子プロセスの間で通信するためには、各プロセスのパイプで開いている記述子を 1 つだけ必要があります。 記述子は正反対である必要があります。親が開いている読み取り記述子を持つ場合、子は開いている書き込み記述子を持つ必要があります。 これを行う最も簡単な方法はビットごとに、または (**|**)、 **_O_NOINHERIT**とフラグ*textmode*です。 使用して、 **_dup**または **_dup2**子に渡すパイプ記述子の継承可能なコピーを作成します。 元の記述子を終了し、子プロセスを生成します。 生成の呼び出しから制御が戻ったら、親プロセスの重複記述子を閉じます。 詳細については、この記事で後述する例 2 を参照してください。

Windows オペレーティング システムでは、すべての記述子が閉じたときパイプは破棄されます。 (パイプですべての読み取り記述子が閉じられた場合、パイプへの書き込みによりエラーが発生します)。パイプでのすべての読み取り操作と書き込み操作は、I/O 要求を完了するために十分なデータまたは十分なバッファー領域が確保されるまで、待機状態になります。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|オプション ヘッダー|
|-------------|---------------------|---------------------|
|**_pipe**|\<io.h>|\<fcntl.h>、1 \<errno.h>2|

1 の **_O_BINARY**と **_O_TEXT**定義します。

2 **errno**定義します。

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md)のすべてのバージョン。

## <a name="example-1"></a>例 1

```C
// crt_pipe.c
/* This program uses the _pipe function to pass streams of
* text to spawned processes.
*/

#include <stdlib.h>
#include <stdio.h>
#include <io.h>
#include <fcntl.h>
#include <process.h>
#include <math.h>

enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */
#define NUMPROBLEM 8

int main( int argc, char *argv[] )
{

   int fdpipe[2];
   char hstr[20];
   int pid, problem, c;
   int termstat;

   /* If no arguments, this is the spawning process */
   if( argc == 1 )
   {

      setvbuf( stdout, NULL, _IONBF, 0 );

      /* Open a set of pipes */
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )
          exit( 1 );

      /* Convert pipe read descriptor to string and pass as argument
       * to spawned program. Program spawns itself (argv[0]).
       */
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],
            hstr, NULL ) ) == -1 )
          printf( "Spawn failed" );

      /* Put problem in write pipe. Since spawned program is
       * running simultaneously, first solutions may be done
       * before last problem is given.
       */
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)
      {

         printf( "Son, what is the square root of %d?\n", problem );
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );

      }

      /* Wait until spawned program is done processing. */
      _cwait( &termstat, pid, WAIT_CHILD );
      if( termstat & 0x0 )
         printf( "Child failed\n" );

      _close( fdpipe[READ] );
      _close( fdpipe[WRITE] );

   }

   /* If there is an argument, this must be the spawned process. */
   else
   {

      /* Convert passed string descriptor to integer descriptor. */
      fdpipe[READ] = atoi( argv[1] );

      /* Read problem from pipe and calculate solution. */
      for( c = 0; c < NUMPROBLEM; c++ )
      {

        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );
        printf( "Dad, the square root of %d is %3.2f.\n",
                 problem, sqrt( ( double )problem ) );

      }
   }
}
```

```Output
Son, what is the square root of 1000?
Son, what is the square root of 2000?
Son, what iDad, the square root of 1000 is 31.62.
Dad, the square root of 2000 is 44.72.
s the square root of 3000?
Dad, the square root of 3000 is 54.77.
Son, what is the square root of 4000?
Dad, the square root of 4000 is 63.25.
Son, what is the square root of 5000?
Dad, the square root of 5000 is 70.71.
Son, what is the square root of 6000?
SonDad, the square root of 6000 is 77.46.
, what is the square root of 7000?
Dad, the square root of 7000 is 83.67.
Son, what is the square root of 8000?
Dad, the square root of 8000 is 89.44.
```

## <a name="example-2"></a>例 2

これは基本的なフィルター アプリケーションです。 これは、生成されたアプリケーションの標準出力をフィルターに指定するパイプを作成した後、アプリケーションの crt_pipe_beeper を生成します。 フィルターは ASCII 7 (ビープ音) 文字を削除します。

```C
// crt_pipe_beeper.c

#include <stdio.h>
#include <string.h>

int main()
{
   int   i;
   for(i=0;i<10;++i)
      {
         printf("This is speaker beep number %d...\n\7", i+1);
      }
   return 0;
}
```

実際のフィルター アプリケーション:

```C
// crt_pipe_BeepFilter.C
// arguments: crt_pipe_beeper.exe

#include <windows.h>
#include <process.h>
#include <memory.h>
#include <string.h>
#include <stdio.h>
#include <fcntl.h>
#include <io.h>

#define   OUT_BUFF_SIZE 512
#define   READ_FD 0
#define   WRITE_FD 1
#define   BEEP_CHAR 7

char szBuffer[OUT_BUFF_SIZE];

int Filter(char* szBuff, ULONG nSize, int nChar)
{
   char* szPos = szBuff + nSize -1;
   char* szEnd = szPos;
   int nRet = nSize;

   while (szPos > szBuff)
   {
      if (*szPos == nChar)
         {
            memmove(szPos, szPos+1, szEnd - szPos);
            --nRet;
         }
      --szPos;
   }
   return nRet;
}

int main(int argc, char** argv)
{
   int nExitCode = STILL_ACTIVE;
   if (argc >= 2)
   {
      HANDLE hProcess;
      int fdStdOut;
      int fdStdOutPipe[2];

      // Create the pipe
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)
         return   1;

      // Duplicate stdout file descriptor (next line will close original)
      fdStdOut = _dup(_fileno(stdout));

      // Duplicate write end of pipe to stdout file descriptor
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)
         return   2;

      // Close original write end of pipe
      _close(fdStdOutPipe[WRITE_FD]);

      // Spawn process
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],
       (const char* const*)&argv[1]);

      // Duplicate copy of original stdout back into stdout
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)
         return   3;

      // Close duplicate copy of original stdout
      _close(fdStdOut);

      if(hProcess)
      {
         int nOutRead;
         while   (nExitCode == STILL_ACTIVE)
         {
            nOutRead = _read(fdStdOutPipe[READ_FD],
             szBuffer, OUT_BUFF_SIZE);
            if(nOutRead)
            {
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);
               fwrite(szBuffer, 1, nOutRead, stdout);
            }

            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))
               return 4;
         }
      }
   }
   return nExitCode;
}
```

```Output
This is speaker beep number 1...
This is speaker beep number 2...
This is speaker beep number 3...
This is speaker beep number 4...
This is speaker beep number 5...
This is speaker beep number 6...
This is speaker beep number 7...
This is speaker beep number 8...
This is speaker beep number 9...
This is speaker beep number 10...
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_open、_wopen](open-wopen.md)<br/>
