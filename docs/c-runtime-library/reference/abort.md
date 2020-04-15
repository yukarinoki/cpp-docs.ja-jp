---
title: を呼び出してプログラム実行を終了する際、
ms.date: 4/2/2020
api_name:
- abort
- _o_abort
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
- Abort
helpviewer_keywords:
- aborting current process
- abort function
- processes, aborting
ms.openlocfilehash: 1f70f54783ce6f6d28fdda028af4fd5a205aeb0b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81350928"
---
# <a name="abort"></a>を呼び出してプログラム実行を終了する際、

現在のプロセスを中止し、エラー コードを返します。

> [!NOTE]
> テストまたはデバッグのシナリオを除き、Microsoft ストア アプリまたはユニバーサル Windows プラットフォーム (UWP) アプリをシャットダウンするには、このメソッドを使用しないでください。 ストア アプリを閉じるプログラムまたは UI の方法は、 [Microsoft Store のポリシー](/legal/windows/agreements/store-policies)に従って許可されていません。 詳しくは[、UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)に関する情報をご覧ください。

## <a name="syntax"></a>構文

```C
void abort( void );
```

## <a name="return-value"></a>戻り値

**abort**は呼び出しプロセスに制御を戻しません。 既定では、中止シグナル ハンドラーが確認され、それが設定されている場合は `SIGABRT` が発生します。 次に**abort**は現在のプロセスを終了し、親プロセスに終了コードを返します。

## <a name="remarks"></a>解説

**マイクロソフト固有**

既定では、デバッグ ランタイム ライブラリを使用してアプリをビルドすると、**中止**ルーチンは、前に`SIGABRT`エラー メッセージが表示されます。 コンソール モードで動作しているコンソール アプリの場合は、`STDERR` にメッセージが送信されます。 ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。 メッセージを抑制するには、[_set_abort_behavior](set-abort-behavior.md) を使用して `_WRITE_ABORT_MSG` フラグをクリアします。 表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。 最新バージョンの Visual C++ を使用してビルドされたアプリケーションの場合、メッセージは次のようになります。

> R6010 - abort() が呼び出されました

C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。

> このアプリケーションは、通常と異なる方法でランタイムにアプリケーションを中止するように要求しました。 詳細については、アプリケーションのサポート チームに問い合わせてください。

プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに [**中止**]、[**再試行**]、または [**無視**] のオプションが表示されます。 ユーザーが [**中止**] をクリックすると、プログラムが即座に終了し、終了コード 3 が返されます。 ユーザーが [**再試行**] をクリックすると、just-in-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。 ユーザーが **[無視**] を選択した場合 **、abort**は通常の処理を続行します。

リテール ビルドとデバッグ ビルドの両方で **、abort**を実行して、中止シグナル ハンドラーが設定されているかどうかを確認します。 デフォルト以外のシグナルハンドラが設定されている場合は、中止`raise(SIGABRT)`呼び出しを**中止**します。 `SIGABRT` シグナルに中止シグナル ハンドラー関数を関連付けるには、[signal](signal.md) 関数を使用します。 ハンドラー関数では、カスタム動作 (リソースのクリーンアップや情報のログ記録など) を実行し、独自のエラー コードを発行してアプリを修了できます。 カスタムシグナルハンドラが定義されていない場合 **、abort**はシグナルを`SIGABRT`発生しません。

既定では、デスクトップ アプリまたはコンソール アプリのデバッグ ビルド以外では、**中止**を中止して Windows エラー報告サービス メカニズム (以前はワトソン博士) を呼び出して、Microsoft にエラーを報告します。 この動作は、`_set_abort_behavior` を呼び出し、`_CALL_REPORTFAULT` フラグを設定するかマスクして、有効または無効にすることができます。 フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。 ユーザーは [**デバッグ**] をクリックしてデバッガーを開始するか、[**プログラムの終了**] をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。

Windows エラー報告ハンドラーが呼び出されない場合は、呼び出しを**中止**[_exit](exit-exit-exit.md)終了コード 3 でプロセスを終了し、親プロセスまたはオペレーティング システムに制御を返します。 `_exit` は、ストリーム バッファーをフラッシュせず、`atexit`/`_onexit` 処理を行いません。

CRT デバッグの詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**END Microsoft 固有の仕様**

既定では、この関数のグローバル状態はアプリケーションにスコープされます。 これを変更するには[、CRT のグローバル状態を](../global-state.md)参照してください。

## <a name="requirements"></a>必要条件

|ルーチン|必須ヘッダー|
|-------------|---------------------|
|**中止**|\<process.h> または \<stdlib.h>|

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
[プロセスと環境の制御](../../c-runtime-library/process-and-environment-control.md)<br/>
[_exec、_wexec 系関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[raise](raise.md)<br/>
[信号](signal.md)<br/>
[_spawn 系関数と _wspawn 系関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_debug](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)
