---
title: _beginthread、_beginthreadex | Microsoft Docs
ms.custom: ''
ms.date: 02/27/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _beginthread
- _beginthreadex
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
- beginthread
- _beginthread
- beginthreadex
- _beginthreadex
dev_langs:
- C++
helpviewer_keywords:
- _beginthread function
- threading [C++], creating threads
- beginthreadex function
- _beginthreadex function
- beginthread function
ms.assetid: 0df64740-a978-4358-a88f-fb0702720091
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d56bcc5ec779b077305d9d80e4a4e6b5e511df5e
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/01/2018
ms.locfileid: "34704660"
---
# <a name="beginthread-beginthreadex"></a>_beginthread、_beginthreadex

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
新しいスレッドの実行を開始するルーチンの開始アドレス。 **_Beginthread**、呼び出し規約を[_ _cdecl](../../cpp/cdecl.md) (ネイティブ コード用または[_ _clrcall](../../cpp/clrcall.md) (マネージ コード) の; **_beginthreadex**、いずれかである[_ _stdcall](../../cpp/stdcall.md) (ネイティブ コード用または[_ _clrcall](../../cpp/clrcall.md) (マネージ コード) 用です。

*stack_size*<br/>
新しいスレッドのスタック サイズまたは 0。

*arglist*<br/>
新しいスレッドに渡される引数リストまたは**NULL**です。

*セキュリティ*<br/>
[SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) 構造体へのポインター。この構造体は、返されたハンドルを子プロセスが継承できるかどうかを決定します。 場合*セキュリティ*は**NULL**ハンドルは継承できません。 必要があります**NULL** Windows 95 アプリケーションです。

*initflag*<br/>
新しいスレッドの初期状態を制御するフラグ。 設定*initflag*をすぐに実行する場合は 0 をまたはに**CREATE_SUSPENDED** ; 中断状態のスレッドを作成するを使用して[ResumeThread](http://msdn.microsoft.com/library/windows/desktop/ms685086.aspx)スレッドを実行します。 設定*initflag*に**STACK_SIZE_PARAM_IS_A_RESERVATION**フラグを使用する*stack_size*初期予約サイズ (バイト単位)、スタックのですこのフラグが指定されていないので、 。*stack_size*によってコミット サイズを指定します。

*thrdaddr*<br/>
スレッド識別子を受け取る 32 ビット変数へのポインター。 場合は**NULL**は使用されません。

## <a name="return-value"></a>戻り値

新しく作成されたスレッド; ハンドルを返します成功した場合、これらの各関数ただし、新しく作成されたスレッドの終了が早すぎる場合 **_beginthread**有効なハンドルを返さない可能性があります。 (「解説」の説明を参照)。エラーが発生した、 **_beginthread** -1 L を返しますと**errno**に設定されている**EAGAIN**スレッドが多すぎるにある場合**EINVAL**引数の場合無効であるかスタック サイズが正しくない、または**EACCES**が不足しているリソース (メモリなど) がある場合。 エラーが発生した、 **_beginthreadex** 0 を返しますと**errno**と **_doserrno**設定されます。

場合*start_address*は**NULL**で説明されているとおり、無効なパラメーター ハンドラーが呼び出されます[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、これらの関数が設定**errno**に**EINVAL**し、-1 を返します。

これらのリターン コードとその他のリターン コードの詳細については、「[errno、_doserrno、_sys_errlist、_sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

詳細については**uintptr_t**を参照してください[スタンダード](../../c-runtime-library/standard-types.md)です。

## <a name="remarks"></a>コメント

**_Beginthread**関数で指定されるルーチンの実行を開始するスレッドを作成する*start_address*です。 あるルーチンは*start_address*を使用する必要があります、 **_ _cdecl** (のネイティブ コード) または **_ _clrcall** (マネージ コード) の呼び出し規約、戻り値はありません。 スレッドは、ルーチンから戻ると自動的に終了します。 スレッドの詳細については、「[旧形式のコードのためのマルチスレッド サポート (Visual C++)](../../parallel/multithreading-support-for-older-code-visual-cpp.md)」を参照してください。

**_beginthreadex** Win32 に似ています[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453.aspx) API より密接に **_beginthread**はします。 **_beginthreadex**異なる **_beginthread**次のようにします。

- **_beginthreadex** 3 つの追加パラメーターを持ち: *initflag*、*セキュリティ*、および**threadaddr**です。 セキュリティを指定で、中断された状態で作成することができを使用してアクセスできる新規スレッド*thrdaddr*は、スレッドの識別子。

- あるルーチンは*start_address*に渡される **_beginthreadex**を使用する必要があります、 **_ _stdcall** (のネイティブ コードの場合) または **_ _clrcall** (マネージ コードの) 呼び出し規則と、スレッドの終了コードを返す必要があります。

- **_beginthreadex** -1 L ではなく、失敗、0 を返します。

- 使用して作成したスレッド **_beginthreadex**への呼び出しで終了[_endthreadex](endthread-endthreadex.md)です。

**_Beginthreadex**関数を使用するよりも、スレッドを作成する方法より詳細に制御 **_beginthread**はします。 **_Endthreadex**関数より柔軟性がもできます。 たとえば、 **_beginthreadex**、セキュリティ情報を使用して、(実行中または中断)、スレッドの初期状態を設定および新しく作成されたスレッドのスレッド識別子を取得することができます。 によって返されたスレッド ハンドルを使用することも **_beginthreadex**同期を行うことはできませんが、Api と共に **_beginthread**です。

使用する方が安全 **_beginthreadex**より **_beginthread**です。 場合によって生成されるスレッド **_beginthread**の呼び出し元に返されるハンドルの終了が早、 **_beginthread**が無効であるか別のスレッドをポイントします。 ただし、によって返されるハンドル **_beginthreadex**の呼び出し元によって閉じられるが **_beginthreadex**場合ハンドルが有効にすることは保証されているため、 **_beginthreadex**エラーを返しませんでした。

呼び出すことができます[_endthread](endthread-endthreadex.md)または **_endthreadex**明示的にスレッドを終了しますただし、 **_endthread**または **_endthreadex**は呼び出されます。自動的に、スレッドを返す場合、パラメーターとして渡されたルーチンからです。 呼び出してスレッドを終了 **_endthread**または **_endthreadex**確実にスレッドに割り当てられるリソースの解放します。

**_endthread**一方、スレッド ハンドルを自動的に閉じる **_endthreadex**しません。 したがって、使用 **_beginthread**と **_endthread**、Win32 の呼び出しを明示的に、スレッド ハンドルを終了しないでください[CloseHandle](http://msdn.microsoft.com/library/windows/desktop/ms724211.aspx) API です。 この動作は、Win32 [ExitThread](http://msdn.microsoft.com/library/windows/desktop/ms682659.aspx) API とは異なります。

> [!NOTE]
> Libcmt.lib にリンクする実行可能ファイルを呼び出す必要はありません、Win32 **ExitThread** API することができなく実行時のシステムを再利用できるようにはリソースを割り当てられます。 **_endthread**と **_endthreadex**割り当てられているスレッド リソースを解放し、呼び出す**ExitThread**です。

オペレーティング システムがスタックの割り当てを処理時にいずれか **_beginthread**または **_beginthreadex**が呼び出されます。 これらの関数のいずれかに、スレッド スタックのアドレスを通過する必要はありません。 さらに、 *stack_size*引数が 0 の場合、オペレーティング システムによって使用される同じ値が指定されているスタックと、メイン スレッドを指定できます。

*arglist*新しく作成されたスレッドに渡されるパラメーターです。 通常、文字列などのデータ項目のアドレスを指定します。 *arglist*できます**NULL**必要でない場合は **_beginthread**と **_beginthreadex**に新しいスレッドに渡すためのいくつかの値を指定する必要があります。 いずれかのスレッドの呼び出しのすべてのスレッドが終了[中止](abort.md)、**終了**、 **_exit**、または**ExitProcess**です。

新しいスレッドのロケールは、プロセスあたりのグローバル現在のロケール情報を使用して初期化されます。 呼び出しによってスレッドごとのロケールが有効になっているかどうかは[_configthreadlocale](configthreadlocale.md) (グローバルまたは新しいスレッドのみ)、スレッドなく変更できますロケール別々 に他のスレッドから呼び出すことによって**setlocale、_wsetlocale**または **_wsetlocale**です。 スレッドごとのロケールのフラグが設定がないスレッドは、設定すると、スレッドごとのロケールのフラグはその他のすべてのスレッドだけでなくすべての新しく作成されたスレッドのロケール情報に影響を与えます。 詳細については、「 [Locale](../../c-runtime-library/locale.md)」を参照してください。

**/Clr**コード、 **_beginthread**と **_beginthreadex**それぞれ 2 つのオーバー ロードがあります。 1 つはネイティブの呼び出し規約関数ポインターと受け取り、もう一方が、 **_ _clrcall**関数ポインター。 最初のオーバーロードは、アプリケーション ドメインセーフではなく、以降もそうなることはありません。 作成している場合 **/clr**マネージ リソースもコードにアクセスする前には、新しいスレッドが正しいアプリケーション ドメインに入ることを確認する必要があります。 そのためには、[call_in_appdomain 関数](../../dotnet/call-in-appdomain-function.md)などを使用します。 2 番目のオーバー ロードはアプリケーション ドメイン セーフです。呼び出し元のアプリケーション ドメイン内に新しく作成されたスレッド、最終的に必ず **_beginthread**または **_beginthreadex**です。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**_beginthread**|\<process.h>|
|**_beginthreadex**|\<process.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="libraries"></a>ライブラリ

[C ランタイム ライブラリ](../../c-runtime-library/crt-library-features.md) のマルチスレッド バージョンのみ。

使用する **_beginthread**または **_beginthreadex**、マルチ スレッドの C ランタイム ライブラリのいずれかのアプリケーションをリンクする必要があります。

## <a name="example"></a>例

次の例で **_beginthread**と **_endthread**です。

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

// Bounce - Thread to create and and control a colored letter that moves
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

次のサンプル コードでは、によって返されたスレッド ハンドルを使用する方法について説明 **_beginthreadex**を同期 API [WaitForSingleObject](http://msdn.microsoft.com/library/windows/desktop/ms687032.aspx)です。 メイン スレッドは、2 番目のスレッドが終了するのを待って処理を継続します。 2 番目のスレッドを呼び出すと **_endthreadex**、シグナル状態に移動するには、そのスレッド オブジェクトになります。 これにより、1 番目のスレッドの実行が継続されます。 これで実行できない **_beginthread**と **_endthread**ので、 **_endthread**呼び出し**CloseHandle**スレッドを破棄します。シグナル状態にする前にオブジェクトを設定することができます。

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

- [プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)
- [_endthread、_endthreadex](endthread-endthreadex.md)
- [abort](abort.md)
- [exit、_Exit、_exit](exit-exit-exit.md)
- [GetExitCodeThread](http://msdn.microsoft.com/library/windows/desktop/ms683190)
