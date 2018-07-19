---
title: signal | Microsoft Docs
ms.custom: ''
ms.date: 04/12/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- signal function
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a87978ec3b0840be6ab1779af86765208c80832c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
ms.locfileid: "32416821"
---
# <a name="signal"></a>signal

割り込みシグナル処理を設定します。

> [!IMPORTANT]
> このメソッドを使用して、テスト シナリオまたはデバッグ シナリオを除く、Microsoft ストアのアプリをシャット ダウンしないでください。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](http://go.microsoft.com/fwlink/?LinkId=865936)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](http://go.microsoft.com/fwlink/p/?LinkId=865934)です。

## <a name="syntax"></a>構文

```C
void __cdecl *signal(int sig, int (*func)(int, int));
```

### <a name="parameters"></a>パラメーター

*sig*<br/>
シグナル値。

*func*<br/>
2 番目のパラメーターは、実行される関数へのポインターです。 最初のパラメーターはシグナル値で、2 番目のパラメーターは、最初のパラメーターが SIGFPE のときに使用できるサブコードです。

## <a name="return-value"></a>戻り値

**信号**指定されたシグナルに関連付けられている func の前の値を返します。 たとえば場合の前の値*func*が**SIG_IGN**、戻り値も**SIG_IGN**です。 戻り値の **、今**はエラーを示します。 その場合は、 **errno**に設定されている**EINVAL**です。

リターン コードの詳細については、「[errno、_doserrno、_sys_errlist、および _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)」を参照してください。

## <a name="remarks"></a>コメント

**信号**関数には、オペレーティング システムからの割り込みシグナルを処理するいくつかの方法のいずれかを選択するためのプロセスが有効にします。 *Sig*引数は、割り込みを**信号**が応答シグナルで定義されている次のマニフェスト定数のいずれかにする必要があります。H.

|*sig*値|説明|
|-----------------|-----------------|
|**SIGABRT**|異常終了|
|**SIGFPE**|浮動小数点エラー|
|**SIGILL**|無効な命令|
|**SIGINT**|Ctrl + C シグナル|
|**SIGSEGV**|ストレージへの無効なアクセス|
|**SIGTERM**|終了要求|

場合*sig*は 1 つで、上記の値の無効なパラメーター ハンドラーが呼び出されるで定義されている[パラメーターの検証](../../c-runtime-library/parameter-validation.md)です。 実行の継続が許可された場合に、この関数が設定**errno**に**EINVAL**し、返します**今**です。

既定では、**信号**の値に関係なく、終了コード 3 で呼び出し元のプログラムを終了*sig*です。

> [!NOTE]
> **SIGINT**は、すべての Win32 アプリケーションはサポートされていません。 Ctrl + C 割り込みが発生すると、Win32 オペレーティング システムは、その割り込みを処理する専用の新しいスレッドを生成します。 これにより、UNIX のアプリケーションなどのシングル スレッド アプリケーションがマルチスレッドになり、予期しない動作が発生する可能性があります。

*Func*引数は、アドレスを記述したシグナル ハンドラーまたは定義済みの定数のいずれかに**SIG_DFL**または**SIG_IGN**信号で定義されています。H. 場合*func*関数は、指定したシグナルのシグナル ハンドラーとしてインストールされます。 シグナル ハンドラーのプロトタイプには、1 つの仮引数が必要です。 *sig*、型の**int**です。オペレーティング システムは使用して実引数*sig*引数は、割り込みを生成したシグナルで割り込みが発生したときにします。 したがって、シグナル ハンドラーで (前の表の) 6 つのマニフェスト定数を使用して、発生した割り込みを特定し、適切なアクションを実行できます。 たとえば、呼び出す**信号**同じハンドラーを 2 つの異なるシグナルに割り当てるし、テストを 2 回、 *sig*受け取ったシグナルに基づいて異なるアクションを実行するハンドラーの引数。

浮動小数点例外用にテストしている場合 (**SIGFPE**)、 *func*省略可能な 2 番目の引数を受け取る関数へのポインターは、浮動小数点数で定義されている複数のマニフェスト定数のいずれか。H、フォームの**FPE_xxx**です。 ときに、 **SIGFPE**シグナルが発生すると、浮動小数点例外の種類を決定し、適切なアクションを実行するには、2 番目の引数の値をテストすることができます。 この引数とその有効な値は Microsoft 拡張機能です。

値、浮動小数点例外用*func*シグナルを受け取ったときにリセットされません。 浮動小数点例外から回復するには、try/except 句で浮動小数点演算を囲みます。 [setjmp](setjmp.md) と [longjmp](longjmp.md) を使用して回復することもできます。 いずれの場合も、呼び出し元プロセスは実行を再開し、プロセスの浮動小数点状態を未定義のままにします。

シグナル ハンドラーが戻った場合、呼び出し元プロセスは、割り込みシグナルを受け取った位置の直後から実行を再開します。 この動作は、どの種類のシグナルまたは動作モードにも当てはまります。

指定された関数が実行される前に、値の*func*に設定されている**SIG_DFL**です。 次の割り込みシグナルがについて説明したように扱われます**SIG_DFL**、間の呼び出しがない限り、**信号**それ以外の場合を指定します。 この機能を使用して、呼び出された関数でシグナルをリセットできます。

シグナル ハンドラー ルーチンは、通常、割り込みの発生時に非同期的に呼び出されるので、実行時の操作が未完了で、不明な状態の場合は、シグナル ハンドラー関数が制御を取得することがあります。 次の一覧に、シグナル ハンドラー ルーチンで使用できる関数が決まる制限事項について説明します。

- 低レベルの問題ないまたは STDIO しないでください。H I/O ルーチン (たとえば、 **printf**または**fread**)。

- ヒープ ルーチンまたはヒープ ルーチンを使用する任意のルーチンを呼び出す必要はありません (たとえば、 **malloc**、 **_strdup**、または **_putenv**)。 詳細については、「[malloc](malloc.md)」を参照してください。

- システム コールを生成する任意の関数を使用しないでください (たとえば、 **_getcwd**または**時間**)。

- 使用しないでください**longjmp**割り込みが浮動小数点の例外が発生した場合を除き、(つまり、 *sig*は**SIGFPE**)。 この場合、最初にパッケージを再初期化、浮動小数点への呼び出しを使用して、 **_fpreset**です。

- オーバーレイ ルーチンを使用しない。

プログラムはトラップする場合は、浮動小数点コードを含める必要があります、 **SIGFPE**関数を使用して例外。 プログラムに浮動小数点コードがなく、ランタイム ライブラリのシグナル処理コードが必要な場合は、次のように volatile double を宣言して、ゼロに初期化します。

```C
volatile double d = 0.0f;
```

**SIGILL**と**SIGTERM**シグナルは Windows では生成されません。 これは、ANSI との互換性を維持するために用意されています。 したがってを使用してこれらのシグナルのシグナル ハンドラーを設定することができます**信号**、呼び出すことによって、これらのシグナルを生成することができますも明示的と[を発生させる](raise.md)です。

シグナル設定はへの呼び出しによって作成される子のプロセスでは保持されません[_exec](../../c-runtime-library/exec-wexec-functions.md)または[_spawn](../../c-runtime-library/spawn-wspawn-functions.md)関数。 シグナル設定は、新しいプロセスでは既定値にリセットされます。

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**signal**|\<signal.h>|

互換性の詳細については、「 [互換性](../../c-runtime-library/compatibility.md)」を参照してください。

## <a name="example"></a>例

次の例は、使用する方法を示しています。**信号**をいくつかのカスタム動作を追加する、 **SIGABRT**信号。 中止動作の詳細については、「[_set_abort_behavior](set-abort-behavior.md)」を参照してください。

```C
// crt_signal.c
// compile with: /EHsc /W4
// Use signal to attach a signal handler to the abort routine
#include <stdlib.h>
#include <signal.h>
#include <tchar.h>

void SignalHandler(int signal)
{
    if (signal == SIGABRT) {
        // abort signal handler code
    } else {
        // ...
    }
}

int main()
{
    typedef void (*SignalHandlerPointer)(int);

    SignalHandlerPointer previousHandler;
    previousHandler = signal(SIGABRT, SignalHandler);

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
