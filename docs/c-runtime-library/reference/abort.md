---
description: '詳細情報: abort'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: a1733cb99fca332a97f59540833d5c48eb258a4e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97303912"
---
# <a name="abort"></a>を呼び出してプログラム実行を終了する際、

現在のプロセスを中止し、エラー コードを返します。

> [!NOTE]
> テストシナリオまたはデバッグシナリオの場合を除き、このメソッドを使用して Microsoft Store アプリまたはユニバーサル Windows プラットフォーム (UWP) アプリをシャットダウンしないでください。 プログラムまたは UI がストアアプリを閉じる方法は、 [Microsoft Store ポリシー](/legal/windows/agreements/store-policies)によっては許可されていません。 詳細については、「 [UWP アプリのライフサイクル](/windows/uwp/launch-resume/app-lifecycle)」を参照してください。

## <a name="syntax"></a>構文

```C
void abort( void );
```

## <a name="return-value"></a>戻り値

**abort** は呼び出し元のプロセスに制御を返しません。 既定では、中止シグナル ハンドラーが確認され、それが設定されている場合は `SIGABRT` が発生します。 その後、 **abort** は現在のプロセスを終了し、親プロセスに終了コードを返します。

## <a name="remarks"></a>Remarks

**Microsoft 固有の仕様**

既定では、デバッグランタイムライブラリを使用してアプリをビルドすると、が発生する前に、 **abort** ルーチンによってエラーメッセージが表示され `SIGABRT` ます。 コンソール モードで動作しているコンソール アプリの場合は、`STDERR` にメッセージが送信されます。 ウィンドウ モードで動作している Windows デスクトップ アプリとコンソール アプリでは、メッセージ ボックスにメッセージが表示されます。 メッセージを抑制するには、[_set_abort_behavior](set-abort-behavior.md) を使用して `_WRITE_ABORT_MSG` フラグをクリアします。 表示されるメッセージは、使用しているランタイム環境のバージョンによって異なります。 最新バージョンの Visual C++ を使用してビルドされたアプリケーションの場合、メッセージは次のようになります。

> R6010-abort () が呼び出されました

C ランタイム ライブラリの以前のバージョンでは、次のメッセージが表示されました。

> このアプリケーションは、通常と異なる方法でランタイムにアプリケーションを中止するように要求しました。 詳細については、アプリケーションのサポート チームに問い合わせてください。

プログラムをデバッグ モードでコンパイルしている場合、メッセージ ボックスに [**中止**]、[**再試行**]、または [**無視**] のオプションが表示されます。 ユーザーが [**中止**] をクリックすると、プログラムが即座に終了し、終了コード 3 が返されます。 ユーザーが [**再試行**] をクリックすると、just-in-time デバッグが有効な場合はデバッガーが起動してデバッグが開始します。 ユーザーが [ **無視**] を選択した場合、 **abort** は通常の処理を続行します。

リテールビルドとデバッグビルドの両方 **で、abort** シグナルハンドラーが設定されているかどうかをチェックします。 既定以外のシグナルハンドラーが設定されている場合は、 **abort** が呼び出さ `raise(SIGABRT)` れます。 `SIGABRT` シグナルに中止シグナル ハンドラー関数を関連付けるには、[signal](signal.md) 関数を使用します。 ハンドラー関数では、カスタム動作 (リソースのクリーンアップや情報のログ記録など) を実行し、独自のエラー コードを発行してアプリを修了できます。 カスタムシグナルハンドラーが定義されていない場合、 **abort** はシグナルを生成しません `SIGABRT` 。

既定では、デスクトップまたはコンソールアプリの非デバッグビルドでは、 **abort** は Windows エラー報告サービスメカニズム (旧称は dr. Watson) を呼び出して、エラーを Microsoft に報告します。 この動作は、`_set_abort_behavior` を呼び出し、`_CALL_REPORTFAULT` フラグを設定するかマスクして、有効または無効にすることができます。 フラグが設定されていると、Windows でメッセージ ボックスが開き、「問題が発生したため、プログラムが正しく動作しなくなりました」などのテキストが表示されます。 ユーザーは [**デバッグ**] をクリックしてデバッガーを開始するか、[**プログラムの終了**] をクリックすることでオペレーティング システムで定義されているエラー コードを発行してアプリを終了できます。

Windows エラー報告ハンドラーが呼び出されていない場合、 **abort** は [_exit](exit-exit-exit.md) を呼び出して終了コード3でプロセスを終了し、親プロセスまたはオペレーティングシステムに制御を戻します。 `_exit` は、ストリーム バッファーをフラッシュせず、`atexit`/`_onexit` 処理を行いません。

CRT デバッグの詳細については、「 [CRT のデバッグ技術](/visualstudio/debugger/crt-debugging-techniques)」を参照してください。

**End Microsoft 固有の仕様**

既定では、この関数のグローバル状態はアプリケーションにスコープが設定されています。 これを変更するには、「 [CRT でのグローバル状態](../global-state.md)」を参照してください。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|**取り消し**|\<process.h> または \<stdlib.h>|

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
[_exec, _wexec 関数](../../c-runtime-library/exec-wexec-functions.md)<br/>
[終了、_Exit、_exit](exit-exit-exit.md)<br/>
[raise](raise.md)<br/>
[signal](signal.md)<br/>
[_spawn, _wspawn 関数](../../c-runtime-library/spawn-wspawn-functions.md)<br/>
[_DEBUG](../../c-runtime-library/debug.md)<br/>
[_set_abort_behavior](set-abort-behavior.md)
