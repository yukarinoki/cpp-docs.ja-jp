---
title: _beginthread、_beginthreadex
ms.date: 4/2/2020
api_name:
- _beginthread
- _beginthreadex
- _o__beginthread
- _o__beginthreadex
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
ms.openlocfilehash: 2d2851a7e76a43501145b1e55e8028b72c2a8afb
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81348677"
---
# <a name="_beginthread-_beginthreadex"></a>_beginthread、_beginthreadex

スレッドを作成します。

## <a name="syntax"></a>構文

```cpp
uintptr_t _beginthread( // NATIVE CODE
   void( __cdecl *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthread( // MANAGED CODE
   void( __clrcall *start_address )( void * ),
   unsigned stack_size,
   void *arglist
);
uintptr_t _beginthreadex( // NATIVE CODE
   void *security,
   unsigned stack_size,
   unsigned ( __stdcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
uintptr_t _beginthreadex( // MANAGED CODE
   void *security,
   unsigned stack_size,
   unsigned ( __clrcall *start_address )( void * ),
   void *arglist,
   unsigned initflag,
   unsigned *thrdaddr
);
```

### <a name="parameters"></a>パラメーター

*start_address*<br/>
新しいスレッドの実行を開始するルーチンの開始アドレス。 **_beginthread**の場合、呼び出し規約は、ネイティブ コードの[場合は__cdecl](../../cpp/cdecl.md)またはマネージ コードの[場合__clrcall](../../cpp/clrcall.md)です。**_beginthreadex**の場合は、ネイティブ コードの[場合は__stdcall](../../cpp/stdcall.md)または[__clrcall](../../cpp/clrcall.md) (マネージ コード用) です。

*stack_size*<br/>
新しいスレッドのスタック サイズまたは 0。

*Arglist*<br/>
新しいスレッドに渡す引数リスト、または**NULL**。

*Security*<br/>
[SECURITY_ATTRIBUTES](/previous-versions/windows/desktop/legacy/aa379560\(v=vs.85\)) 構造体へのポインター。この構造体は、返されたハンドルを子プロセスが継承できるかどうかを決定します。 *セキュリティ*が**NULL**の場合、ハンドルは継承できません。 Windows 95 アプリケーションの場合は**NULL である**必要があります。

*イニトフラグ*<br/>
新しいスレッドの初期状態を制御するフラグ。 *initflag*を 0 に設定すると、即**座に実行**されるか、CREATE_SUSPENDED中断状態のスレッドを作成できます。スレッドを実行するには[、ResumeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-resumethread)を使用します。 stack_sizeをバイト単位**STACK_SIZE_PARAM_IS_A_RESERVATION**スタックの初期予約*サイズとして使用*するには *、initflag*をフラグに設定します。このフラグが指定されていない場合 *、stack_size*はコミット・サイズを指定します。

*スルダドル*<br/>
スレッド識別子を受け取る 32 ビット変数へのポインター。 **NULL**の場合は使用されません。

## <a name="return-value"></a>戻り値

成功した場合、これらの各関数は、新しく作成されたスレッドへのハンドルを返します。ただし、新しく作成されたスレッドが早く終了すると **、_beginthread**は有効なハンドルを返さない可能性があります。 (解説のセクションの説明を参照してください)。エラーの場合 **、_beginthread**は -1L を返し、スレッドが多すぎる場合は**errno**が**EAGAIN**に設定され、引数が無効であるかスタック・サイズが正しくない場合は**EINVAL**に、リソース (メモリーなど) が不足している場合は**EACCES**に設定されます。 エラーの場合 **、_beginthreadex**は 0 を返し **、errno**と **_doserrno**が設定されます。

*start_address*が**NULL**の場合は、「パラメータ[の検証](../../c-runtime-library/parameter-validation.md)」で説明されているように、無効なパラメータ ハンドラが呼び出されます。 実行を続行できる場合、これらの関数は**errno**を**EINVAL**に設定し、-1 を返します。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

**uintptr_t**の詳細については、「[標準の型](../../c-runtime-library/standard-types.md)」を参照してください。

## <a name="remarks"></a>解説

**_beginthread**関数は *、start_address*でルーチンの実行を開始するスレッドを作成します。 *start_address*のルーチンは **、__cdecl** (ネイティブ コードの場合) または **__clrcall** (マネージ コードの場合) 呼び出し規約を使用する必要があり、戻り値を持たない必要があります。 スレッドは、ルーチンから戻ると自動的に終了します。 スレッドの詳細については、「[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

**_beginthreadex**は **、_beginthread**よりも Win32 [CreateThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-createthread) API に似ています。 **_beginthreadex**は **、次**の点で_beginthreadとは異なります。

- **_beginthreadex**には、3 つのパラメータがあります: *initflag*、*セキュリティ*、および**スレッドアドル**。 新しいスレッドは、指定されたセキュリティで中断状態で作成でき、スレッド識別子である*thrdaddr*を使用してアクセスできます。

- **_beginthreadex**に渡される*start_address*のルーチンは **、__stdcall** (ネイティブ コードの場合) または **__clrcall** (マネージ コードの場合) 呼び出し規約を使用し、スレッド終了コードを返す必要があります。

- **_beginthreadex**は、エラーが発生した場合に 0 を返します。

- **_beginthreadex**を使用して作成されたスレッドは、 [_endthreadex](endthread-endthreadex.md)の呼び出しによって終了されます。

**_beginthreadex**関数を使用すると、_beginthreadよりもスレッドの作成方法をより詳細**に**制御できます。 **_endthreadex**機能も柔軟性が高くなります。 たとえば、 **_beginthreadex**を使用すると、セキュリティ情報を使用し、スレッドの初期状態 (実行中または中断) を設定し、新しく作成されたスレッドのスレッド ID を取得できます。 同期 API では **、_beginthreadex**によって返されるスレッド ハンドルを使用することもできます **_beginthread。**

_beginthreadよりも **_beginthreadex**を使う方**が**安全です。 **_beginthread**によって生成されたスレッドがすぐに終了する場合 **、_beginthread**の呼び出し元に返されるハンドルが無効であるか、別のスレッドを指している可能性があります。 ただし **、_beginthreadex**によって返されるハンドルは **_beginthreadex**の呼び出し元によって閉じる必要があるため **、_beginthreadex**がエラーを返さなかった場合は、有効なハンドルであることが保証されます。

[_endthread](endthread-endthreadex.md)呼び出したり **、スレッドを終了_endthreadex**明示的に呼び出したりできます。ただし **、_endthread**または **_endthreadex**は、スレッドがパラメーターとして渡されたルーチンから戻ったときに自動的に呼び出されます。 **_endthread**または **_endthreadex**の呼び出しでスレッドを終了すると、スレッドに割り当てられているリソースを確実に回復できます。

**_endthread**はスレッド ハンドルを自動的に閉じますが **、_endthreadex**は閉じません。 したがって **、_beginthread**を使用して **_endthread**場合は、Win32 [CloseHandle](/windows/win32/api/handleapi/nf-handleapi-closehandle) API を呼び出してスレッド ハンドルを明示的に閉じないでください。 この動作は、Win32 [ExitThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-exitthread) API とは異なります。

> [!NOTE]
> Libcmt.lib にリンクされた実行可能ファイルの場合は、Win32 **ExitThread** API を呼び出さないでください。 **割**り当てられたスレッド リソース**を**_endthreadし、_endthreadexし **、ExitThread**を呼び出します。

オペレーティング システムは **、_beginthread**または **_beginthreadex**が呼び出されたときに、スタックの割り当てを処理します。これらの関数のいずれかにスレッド スタックのアドレスを渡す必要はありません。 また *、stack_size*引数は 0 にすることができ、その場合、オペレーティング システムはメイン スレッドに指定されているスタックと同じ値を使用します。

*arglist*は、新しく作成されたスレッドに渡されるパラメータです。 通常、文字列などのデータ項目のアドレスを指定します。 *arglist*は必要ない場合は**NULL**でもかまいませんが **、_beginthread**と **_beginthreadex**は新しいスレッドに渡す値を与える必要があります。 中止[、](abort.md)**終了**、 **_exit**、または**ExitProcess**を呼び出すスレッドがある場合、すべてのスレッドが終了します。

新しいスレッドのロケールは、プロセスごとのグローバル現在のロケール情報を使用して初期化されます。 スレッドごとのロケールが[_configthreadlocale](configthreadlocale.md)の呼び出しによって有効になっている場合 (グローバルまたは新規スレッドのみ)、スレッドは**setlocale**または **_wsetlocale**を呼び出すことによって、他のスレッドから独立してロケールを変更できます。 スレッドごとのロケール フラグが設定されていないスレッドは、スレッドごとのロケール フラグが設定されていない他のすべてのスレッドのロケール情報と、新しく作成されたすべてのスレッドに影響を与える可能性があります。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**/clr**コードの場合 **、_beginthread**と **_beginthreadex**それぞれに 2 つのオーバーロードがあります。 一方はネイティブ呼び出し規約関数ポインターを受け取り、もう一方は **__clrcall**関数ポインターを受け取ります。 最初のオーバーロードは、アプリケーション ドメインセーフではなく、以降もそうなることはありません。 **/clr**コードを記述する場合は、マネージ リソースにアクセスする前に、新しいスレッドが正しいアプリケーション ドメインに入っていることを確認する必要があります。 そのためには、[call_in_appdomain 関数](../../dotnet/call-in-appdomain-function.md)などを使用します。 2 番目のオーバーロードは、アプリケーション ドメイン セーフです。新しく作成されたスレッドは、常に **_beginthread**または **_beginthreadex**の呼び出し元のアプリケーション ドメインに入ります。

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

互換性について詳しくは、「 [Compatibility](../../c-runtime-library/compatibility.md)」をご覧ください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。

**_beginthread**または **_beginthreadex**を使用するには、アプリケーションがマルチスレッド C ランタイム ライブラリの 1 つとリンクしている必要があります。

## <a name="example"></a>例

次の例では **、_beginthread**と **_endthread**を使用しています。

```C
// crt_BEGTHRD.C
// compile with: /MT /D "_X86_" /c
// processor: x86
#include <windows.h>
#include <process.h>    /* _beginthread, _endthread */
#include <stddef.h>
#include <stdlib.h>
#include <conio.h>

void Bounce( void * );
void CheckKey( void * );

// GetRandom returns a random integer between min and max.
#define GetRandom( min, max ) ((rand() % (int)(((max) + 1) - (min))) + (min))
// GetGlyph returns a printable ASCII character value
#define GetGlyph( val ) ((char)((val + 32) % 93 + 33))

BOOL repeat = TRUE;                 // Global repeat flag
HANDLE hStdOut;                     // Handle for console window
CONSOLE_SCREEN_BUFFER_INFO csbi;    // Console information structure

int main()
{
    int param = 0;
    int * pparam = &param;

    // Get display screen's text row and column information.
    hStdOut = GetStdHandle( STD_OUTPUT_HANDLE );
    GetConsoleScreenBufferInfo( hStdOut, &csbi );

    // Launch CheckKey thread to check for terminating keystroke.
    _beginthread( CheckKey, 0, NULL );

    // Loop until CheckKey terminates program or 1000 threads created.
    while( repeat && param < 1000 )
    {
        // launch another character thread.
        _beginthread( Bounce, 0, (void *) pparam );

        // increment the thread parameter
        param++;

        // Wait one second between loops.
        Sleep( 1000L );
    }
}

// CheckKey - Thread to wait for a keystroke, then clear repeat flag.
void CheckKey( void * ignored )
{
    _getch();
    repeat = 0;    // _endthread implied
}

// Bounce - Thread to create and control a colored letter that moves
// around on the screen.
//
// Params: parg - the value to create the character from
void Bounce( void * parg )
{
    char       blankcell = 0x20;
    CHAR_INFO  ci;
    COORD      oldcoord, cellsize, origin;
    DWORD      result;
    SMALL_RECT region;

    cellsize.X = cellsize.Y = 1;
    origin.X = origin.Y = 0;

    // Generate location, letter and color attribute from thread argument.
    srand( _threadid );
    oldcoord.X = region.Left = region.Right =
        GetRandom(csbi.srWindow.Left, csbi.srWindow.Right - 1);
    oldcoord.Y = region.Top = region.Bottom =
        GetRandom(csbi.srWindow.Top, csbi.srWindow.Bottom - 1);
    ci.Char.AsciiChar = GetGlyph(*((int *)parg));
    ci.Attributes = GetRandom(1, 15);

    while (repeat)
    {
        // Pause between loops.
        Sleep( 100L );

        // Blank out our old position on the screen, and draw new letter.
        WriteConsoleOutputCharacterA(hStdOut, &blankcell, 1, oldcoord, &result);
        WriteConsoleOutputA(hStdOut, &ci, cellsize, origin, &region);

        // Increment the coordinate for next placement of the block.
        oldcoord.X = region.Left;
        oldcoord.Y = region.Top;
        region.Left = region.Right += GetRandom(-1, 1);
        region.Top = region.Bottom += GetRandom(-1, 1);

        // Correct placement (and beep) if about to go off the screen.
        if (region.Left < csbi.srWindow.Left)
            region.Left = region.Right = csbi.srWindow.Left + 1;
        else if (region.Right >= csbi.srWindow.Right)
            region.Left = region.Right = csbi.srWindow.Right - 2;
        else if (region.Top < csbi.srWindow.Top)
            region.Top = region.Bottom = csbi.srWindow.Top + 1;
        else if (region.Bottom >= csbi.srWindow.Bottom)
            region.Top = region.Bottom = csbi.srWindow.Bottom - 2;

        // If not at a screen border, continue, otherwise beep.
        else
            continue;
        Beep((ci.Char.AsciiChar - 'A') * 100, 175);
    }
    // _endthread given to terminate
    _endthread();
}
```

任意のキーを押してサンプル アプリケーションを終了します。

## <a name="example"></a>例

次のサンプル コードは、同期 API [WaitForSingleObject](/windows/win32/api/synchapi/nf-synchapi-waitforsingleobject)で **_beginthreadex**によって返されるスレッド ハンドルを使用する方法を示しています。 メイン スレッドは、2 番目のスレッドが終了するのを待って処理を継続します。 2 番目のスレッドが **_endthreadex**を呼び出すと、スレッド オブジェクトはシグナル状態になります。 これにより、1 番目のスレッドの実行が継続されます。 シグナルステートに設定する前にスレッド オブジェクトを破棄する**CloseHandle**を呼び出 **_endthread、_beginthread**と **_endthread**では実行できません。 **_beginthread**

```cpp
// crt_begthrdex.cpp
// compile with: /MT
#include <windows.h>
#include <stdio.h>
#include <process.h>

unsigned Counter;
unsigned __stdcall SecondThreadFunc( void* pArguments )
{
    printf( "In second thread...\n" );

    while ( Counter < 1000000 )
        Counter++;

    _endthreadex( 0 );
    return 0;
}

int main()
{
    HANDLE hThread;
    unsigned threadID;

    printf( "Creating second thread...\n" );

    // Create the second thread.
    hThread = (HANDLE)_beginthreadex( NULL, 0, &SecondThreadFunc, NULL, 0, &threadID );

    // Wait until second thread terminates. If you comment out the line
    // below, Counter will not be correct because the thread has not
    // terminated, and Counter most likely has not been incremented to
    // 1000000 yet.
    WaitForSingleObject( hThread, INFINITE );
    printf( "Counter should be 1000000; it is-> %d\n", Counter );
    // Destroy the thread object.
    CloseHandle( hThread );
}
```

```Output
Creating second thread...
In second thread...
Counter should be 1000000; it is-> 1000000
```

## <a name="see-also"></a>関連項目

- [プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)
- [_endthread、_endthreadex](endthread-endthreadex.md)
- [中止](abort.md)
- [終了、_Exit、_exit](exit-exit-exit.md)
- [GetExitCodeThread](/windows/win32/api/processthreadsapi/nf-processthreadsapi-getexitcodethread)
