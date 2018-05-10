---
title: abort | Microsoft Docs
ms.custom: ''
ms.date: 1/02/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 943faab6b13f3d07b2ca19d78c555973149aa4b0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/03/2018
---
# <a name="abort"></a>を呼び出してプログラム実行を終了する際、

現在のプロセスを中止し、エラー コードを返します。

> [!NOTE]
> このメソッドを使用して、テスト シナリオまたはデバッグ シナリオを除く、Microsoft ストア アプリまたはユニバーサル Windows プラットフォーム (UWP) アプリをシャット ダウンしないでください。 ストア アプリを閉じる方法はプログラムや UI はに従って許可されていません、 [Microsoft ストアのポリシー](/legal/windows/agreements/store-policies)です。 詳細については、次を参照してください。 [UWP アプリのライフ サイクル](/windows/uwp/launch-resume/app-lifecycle)です。

## <a name="syntax"></a>構文

```c
void abort( void );
```

## <a name="return-value"></a>戻り値

**中止**が呼び出しプロセスに制御が返されない。 既定をチェック、中止シグナル ハンドラーと**SIGABRT**が設定されている場合。 **中止**現在のプロセスを終了し、親プロセスに終了コードを返します。

## <a name="remarks"></a>コメント

**Microsoft 固有の仕様**

既定では、アプリがデバッグ ランタイム ライブラリでビルドされたときに、**中止**ルーチンには、前にエラー メッセージが表示されます。 **SIGABRT**が発生します。 コンソール アプリのコンソール モードで実行されている場合に、メッセージは送信**STDERR**です。 ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。 メッセージを抑制するのには、使用[_set_abort_behavior](set-abort-behavior.md)をクリアする、 **_WRITE_ABORT_MSG**フラグ。 表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。 Visual C の最新バージョンを使用してビルドされたアプリケーションでは、メッセージのようになります。

> R6010 - abort() が呼び出されました

C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。

> このアプリケーションは、通常と異なる方法でランタイムにアプリケーションを中止するように要求しました。 詳細については、アプリケーションのサポート チームに問い合わせてください。

プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに **[中止]**、**[再試行]**、または **[無視]** のオプションが表示されます。 ユーザーが **[中止]** をクリックすると、プログラムが即座に終了し、終了コード 3 が返されます。 ユーザーが **[再試行]** をクリックすると、just-in-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。 ユーザーが選択した場合**無視**、**中止**が通常の処理を続行します。

製品版とデバッグ ビルドでは、**中止**し、中止シグナル ハンドラーが設定されているかどうかを確認します。 既定以外のシグナル ハンドラーが設定されている場合**中止**呼び出し`raise(SIGABRT)`です。 使用して、[信号](signal.md)関数に、中止シグナル ハンドラー関数を関連付けるには、 **SIGABRT**信号。 ハンドラー関数では、カスタム動作 (リソースのクリーンアップや情報のログ記録など) を実行し、独自のエラー コードを発行してアプリを修了できます。 カスタムのシグナル ハンドラーが定義されていない場合**中止**は発生しません、 **SIGABRT**信号。

既定では、デスクトップまたはコンソール アプリの非デバッグ ビルドで**中止**(災害復旧と呼ばれていました Windows エラー報告サービス メカニズム呼び出します。ワトソン博士) を起動してエラーを Microsoft に報告します。 この動作を有効になっているか、呼び出すことによって無効になっている **_set_abort_behavior**および設定するかマスク、 **_CALL_REPORTFAULT**フラグ。 フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。 ユーザーは **[デバッグ]** をクリックしてデバッガーを開始するか、**[プログラムの終了]** をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。

Windows エラー レポート ハンドラーが呼び出されない場合、**中止**呼び出し[_exit](exit-exit-exit.md)終了コード 3 を返します管理と、親プロセスまたはオペレーティング システムにプロセスを終了します。 **_exit**しないでまたはストリーム バッファーをフラッシュしません**atexit**/**_onexit**を処理します。

CRT デバッグの詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**END Microsoft 固有の仕様**

## <a name="requirements"></a>要件

|ルーチン|必須ヘッダー|
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
[_set_abort_behavior](set-abort-behavior.md)<br/>
