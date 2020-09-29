---
title: '方法: 遅延後に完了するタスクを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 80bfdeb7586f9c32592bc408a9de0c9188b77a29
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413789"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>方法: 遅延後に完了するタスクを作成する

この例では、 [concurrency:: task](../../parallel/concrt/reference/task-class.md)、 [concurrency:: cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)、 [concurrency:: cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)、concurrency [:: task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)、 [concurrency:: timer](../../parallel/concrt/reference/timer-class.md)、および [concurrency:: call](../../parallel/concrt/reference/call-class.md) クラスを使用して、遅延後に完了するタスクを作成する方法を示します。 このメソッドを使用すると、定期的にデータをポーリングするループを作成したり、タイムアウトを導入したり、事前に定義された時間にユーザー入力の処理を遅延させることができます。

## <a name="example-complete_after-and-cancel_after_timeout-functions"></a>例: complete_after および cancel_after_timeout 関数

`complete_after` 関数および `cancel_after_timeout` 関数の例を次に示します。 関数は、 `complete_after` `task` 指定された遅延の後に完了するオブジェクトを作成します。 オブジェクトとオブジェクトを使用して、 `timer` `call` `task_completion_event` 指定された遅延の後にオブジェクトを設定します。 クラスを使用 `task_completion_event` すると、スレッドまたは別のタスクによって値が使用可能であることが通知された後に完了するタスクを定義できます。 イベントが設定されると、リスナータスクが完了し、その継続が実行されるようにスケジュールされます。

> [!TIP]
> `timer`非同期エージェントライブラリの一部であるおよびクラスの詳細につい `call` ては、「[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

関数は、 `cancel_after_timeout` `complete_after` 指定されたタイムアウトの前にタスクが完了しない場合に、タスクをキャンセルする関数をビルドします。 `cancel_after_timeout`関数は2つのタスクを作成します。 最初のタスクは成功を示し、指定されたタスクが完了した後に完了します。2番目のタスクは失敗を示し、指定されたタイムアウトの後に完了します。 関数は、 `cancel_after_timeout` 成功または失敗のタスクが完了したときに実行される継続タスクを作成します。 エラータスクが最初に完了した場合、継続はトークンソースをキャンセルしてタスク全体を取り消します。

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example-compute-count-of-prime-numbers"></a>例: 素数の計算数

次の例では、範囲 [0, 10万] の素数の数を複数回計算しています。 指定された制限時間内に完了しなかった場合、操作は失敗します。 関数は `count_primes` 、関数の使用方法を示して `cancel_after_timeout` います。 指定された範囲の primes の数をカウントし、指定された時間内にタスクが完了しない場合は失敗します。 関数は、 `wmain` `count_primes` 関数を複数回呼び出します。 そのたびに、時間制限が半分になります。 現在の制限時間内に操作が完了しないと、プログラムは終了します。

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

この手法を使用して遅延後にタスクを取り消すと、タスク全体が取り消された後に、未開始のタスクが開始されません。 ただし、長時間実行されるタスクは、キャンセルに迅速に応答することが重要です。 タスクのキャンセルの詳細については、「 [PPL における取り消し](cancellation-in-the-ppl.md)処理」を参照してください。

## <a name="complete-code-example"></a>完全なコード例

この例の完全なコードを次に示します。

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `task-delay.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

**cl.exe/EHsc task-delay**

## <a name="see-also"></a>関連項目

[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[task クラス (同時実行ランタイム)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token クラス](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[timer クラス](../../parallel/concrt/reference/timer-class.md)<br/>
[call クラス](../../parallel/concrt/reference/call-class.md)<br/>
[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)
