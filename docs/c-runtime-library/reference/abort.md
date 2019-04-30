---
title: を呼び出してプログラム実行を終了する際、
ms.date: 1/02/2018
apiname:
- abort
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
- Abort
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.openlocfilehash: d8cb190e36a64e8bd8cfcb75bc9a19c2a394fc48
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62342199"
---
# <a name="abort"></a>を呼び出してプログラム実行を終了する際、

現在のプロセスを中止し、エラー コードを返します。

> [!NOTE]
> テスト シナリオまたはデバッグ シナリオでは、を除き、Microsoft Store アプリまたはユニバーサル Windows プラットフォーム (UWP) アプリをシャット ダウンは、このメソッドを使用しないでください。 ストア アプリを終了するプログラムや UI の方法はに従って許可されていません、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)します。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)します。

## <a name="syntax"></a>構文

```C
void abort( void );
```

## <a name="return-value"></a>戻り値

**中止**呼び出し元のプロセスに制御が返されない。 既定では、中止シグナル ハンドラーが確認され、それが設定されている場合は `SIGABRT` が発生します。 **中止**現在のプロセスを終了し、親プロセス終了コードを返します。

## <a name="remarks"></a>Remarks

**Microsoft 固有の仕様**

既定で、デバッグ ランタイム ライブラリとアプリのビルド時に、**中止**ルーチンには、前にエラー メッセージが表示されます。`SIGABRT`が発生します。 コンソール モードで動作しているコンソール アプリの場合は、`STDERR` にメッセージが送信されます。 ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。 メッセージを抑制するには、[_set_abort_behavior](set-abort-behavior.md) を使用して `_WRITE_ABORT_MSG` フラグをクリアします。 表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。 Visual C の最新バージョンを使用して構築されたアプリケーションでは、メッセージにこのようになります。

> R6010 - abort() が呼び出されました

C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。

> このアプリケーションは、通常と異なる方法でランタイムにアプリケーションを中止するように要求しました。 詳細については、アプリケーションのサポート チームに問い合わせてください。

プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに **[中止]**、**[再試行]**、または **[無視]** のオプションが表示されます。 ユーザーが **[中止]** をクリックすると、プログラムが即座に終了し、終了コード 3 が返されます。 ユーザーが **[再試行]** をクリックすると、just-in-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。 ユーザーが選択した場合**無視**、**中止**は通常の処理を続行します。

両方の製品版とデバッグ ビルドで**中止**し、中止シグナル ハンドラーが設定されているかどうかを確認します。 既定以外のシグナル ハンドラーが設定されている場合**中止**呼び出し`raise(SIGABRT)`します。 `SIGABRT` シグナルに中止シグナル ハンドラー関数を関連付けるには、[signal](signal.md) 関数を使用します。 ハンドラー関数では、カスタム動作 (リソースのクリーンアップや情報のログ記録など) を実行し、独自のエラー コードを発行してアプリを修了できます。 カスタムのシグナル ハンドラーが定義されていない場合**中止**は発生しません、`SIGABRT`信号。

既定では、デスクトップまたはコンソール アプリの非デバッグ ビルドで**中止**(災害復旧と呼ばれていました Windows エラー報告サービス メカニズムが呼び出され。ワトソン博士) を起動してエラーを Microsoft に報告します。 この動作は、`_set_abort_behavior` を呼び出し、`_CALL_REPORTFAULT` フラグを設定するかマスクして、有効または無効にすることができます。 フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。 ユーザーは **[デバッグ]** をクリックしてデバッガーを開始するか、**[プログラムの終了]** をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。

Windows エラー レポート ハンドラーが呼び出されない場合、し**中止**呼び出し[_exit](exit-exit-exit.md)を親プロセスまたはオペレーティング システムの終了コード 3 を返します管理プロセスを終了します。 `_exit` は、ストリーム バッファーをフラッシュせず、`atexit`/`_onexit` 処理を行いません。

CRT デバッグの詳細については、「[CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**END Microsoft 固有の仕様**

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**abort**|\<process.h> または \<stdlib.h>|

## <a name="example"></a>例

次のプログラムはファイルを開こうとしますが、試みに失敗すると中止されます。

```C
// crt_abort.c
// compile with: /TC
// This program demonstrates the use of
// the abort function by attempting to open a file
// and aborts if the attempt fails.

#include  <stdio.h>
#include  <stdlib.h>

int main( void )
{
    FILE    *stream = NULL;
    errno_t err = 0;

    err = fopen_s(&stream, "NOSUCHF.ILE", "r" );
    if ((err != 0) || (stream == NULL))
    {
        perror( "File could not be opened" );
        abort();
    }
    else
    {
        fclose( stream );
    }
}
```

```Output
File could not be opened: No such file or directory
```

## <a name="see-also"></a>関連項目

[abort の使用](../../cpp/using-abort.md)<br/>
[abort 関数](../../c-language/abort-function-c.md)<br/>
[プロセス制御と環境制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[exit、_Exit、_exit](exit-exit-exit.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)