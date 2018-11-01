---
title: signal
ms.date: 04/12/2018
apiname:
- signal
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
- signal
helpviewer_keywords:
- signal function
ms.openlocfilehash: 1a0f9f8448149ce18155e0f5b88343c56d9b3d7c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660708"
---
# <a name="signal"></a>signal

割り込みシグナル処理を設定します。

> [!IMPORTANT]
> テストまたはデバッグ シナリオにを除き、Microsoft Store アプリをシャット ダウンは、このメソッドを使用しないでください。 ストア アプリを終了するプログラムや UI の方法はに従って許可されていません、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)します。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)します。

## <a name="syntax"></a>構文

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>パラメーター

*sig*<br/>
シグナル値。

*func*<br/>
2 番目のパラメーターは、実行する関数へのポインターです。 最初のパラメーターはシグナル値で、2 番目のパラメーターは、最初のパラメーターが SIGFPE のときに使用できるサブコードです。

## <a name="return-value"></a>戻り値

**シグナル**func に関連付けられた、指定されたシグナルの前の値を返します。 たとえば場合の以前の値*func*が**SIG_IGN**、戻り値も**SIG_IGN**します。 戻り値**今**はエラーを示します。 その場合、 **errno**に設定されている**EINVAL**します。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>Remarks

**信号**関数は、オペレーティング システムからの割り込みシグナルを処理するいくつかの方法のいずれかを選択するプロセスを有効にします。 *Sig*引数がする割り込み**信号**; が応答シグナルで定義されている次のマニフェスト定数のいずれかの必要があります。H.

|*sig*値|説明|
|-----------------|-----------------|
|**SIGABRT**|異常終了|
|**SIGFPE**|浮動小数点エラー|
|**SIGILL**|無効な命令|
|**SIGINT**|Ctrl + C シグナル|
|**SIGSEGV**|ストレージへの無効なアクセス|
|**SIGTERM**|終了要求|

場合*sig*がいずれかで定義されているは、上記の値では、無効なパラメーター ハンドラーが呼び出される[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**返します**今**します。

既定では、**信号**の値に関係なく、終了コード 3 で呼び出し元のプログラムを終了します*sig*します。

> [!NOTE]
> **SIGINT**は、すべての Win32 アプリケーションではサポートされていません。 Ctrl + C 割り込みが発生すると、Win32 オペレーティング システムは、その割り込みを処理する専用の新しいスレッドを生成します。 これにより、UNIX のアプリケーションなどのシングル スレッド アプリケーションがマルチスレッドになり、予期しない動作が発生する可能性があります。

*Func*引数は、アドレスを記述したシグナル ハンドラー、または定義済みの定数のいずれかに**SIG_DFL**または**SIG_IGN**信号でも定義されています。H. 場合*func*関数の場合は、指定されたシグナルのシグナル ハンドラーとしてインストールされます。 シグナル ハンドラーのプロトタイプは、1 つの仮引数を必要と*sig*、型の**int**します。オペレーティング システムは、実際の引数を使用*sig*割り込みが発生した場合は、割り込みを生成したシグナルが、引数が。 したがって、シグナル ハンドラーで (前の表の) 6 つのマニフェスト定数を使用して、発生した割り込みを特定し、適切なアクションを実行できます。 たとえば、呼び出すことができます**信号**2 つの異なるシグナルに同じハンドラーを割り当てるし、テストを 2 回、 *sig*受け取ったシグナルに基づいて異なるアクションを実行するハンドラーの引数。

浮動小数点例外をテストする場合 (**SIGFPE**)、 *func*省略可能な 2 番目の引数を受け取る関数へのポインターは、浮動小数点数で定義されているいくつかのマニフェスト定数のいずれか。H、フォームの**FPE_xxx**します。 ときに、 **SIGFPE**シグナルが発生すると、浮動小数点例外の種類を特定し、適切な処置を実行するには、2 番目の引数の値をテストすることができます。 この引数とその有効な値は Microsoft 拡張機能です。

値の浮動小数点例外用*func*シグナルを受信したときにリセットされません。 浮動小数点例外から回復するには、try/except 句で浮動小数点演算を囲みます。 [setjmp](setjmp.md) と [longjmp](longjmp.md) を使用して回復することもできます。 いずれの場合も、呼び出し元プロセスは実行を再開し、プロセスの浮動小数点状態を未定義のままにします。

シグナル ハンドラーが戻った場合、呼び出し元プロセスは、割り込みシグナルを受け取った位置の直後から実行を再開します。 この動作は、どの種類のシグナルまたは動作モードにも当てはまります。

指定した関数が実行される前に、値の*func*に設定されている**SIG_DFL**します。 説明に従って、次の割り込みシグナルが扱われる**SIG_DFL**その前の呼び出しがない限り、**信号**それ以外の場合を指定します。 この機能を使用して、呼び出された関数でシグナルをリセットできます。

シグナル ハンドラー ルーチンは、通常、割り込みの発生時に非同期的に呼び出されるので、実行時の操作が未完了で、不明な状態の場合は、シグナル ハンドラー関数が制御を取得することがあります。 次の一覧に、シグナル ハンドラー ルーチンで使用できる関数が決まる制限事項について説明します。

- 低レベルの問題ありませんまたは STDIO の操作を行います。H I/O ルーチン (たとえば、 **printf**または**fread**)。

- ヒープ ルーチンまたはヒープ ルーチンを使用する任意のルーチンを呼び出しません (たとえば、 **malloc**、 **_strdup**、または **_putenv**)。 詳細については、「[malloc](malloc.md)」を参照してください。

- システム コールを生成する関数を使用しないでください (たとえば、 **_getcwd**または**時間**)。

- 使用しない**longjmp** 、割り込みが浮動小数点例外によって発生した場合を除き、(つまり、 *sig*は**SIGFPE**)。 この場合は、まずパッケージを再初期化、浮動小数点への呼び出しを使用して **_fpreset**します。

- オーバーレイ ルーチンを使用しない。

プログラムはトラップする場合は、浮動小数点コードを含める必要があります、 **SIGFPE**関数を使用して例外。 プログラムに浮動小数点コードがなく、ランタイム ライブラリのシグナル処理コードが必要な場合は、次のように volatile double を宣言して、ゼロに初期化します。

```C
volatile double d = 0.0f;
```

**SIGILL**と**SIGTERM**信号は、Windows では生成されません。 これは、ANSI との互換性を維持するために用意されています。 使用して、これらのシグナルのシグナル ハンドラーを設定するため、**信号**も明示的に呼び出すことによってこれらのシグナルを生成することができますと[を発生させる](raise.md)します。

呼び出しによって作成された子プロセスでシグナル設定が保持されません[_exec](../../c-runtime-library/exec-wexec-functions.md)または[_spawn](../../c-runtime-library/spawn-wspawn-functions.md)関数。 シグナル設定は、新しいプロセスでは既定値にリセットされます。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**signal**|\<signal.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

次の例は、使用する方法を示します**信号**にいくつかのカスタム動作を追加する、 **SIGABRT**信号。 中止動作の詳細については、「[_set_abort_behavior](set-abort-behavior.md)」を参照してください。

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

    abort();
}
```

```Output
This application has requested the Runtime to terminate it in an unusual way.
Please contact the application's support team for more information.
```

## <a name="see-also"></a>関連項目

[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[abort](abort.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[_fpreset](fpreset.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
