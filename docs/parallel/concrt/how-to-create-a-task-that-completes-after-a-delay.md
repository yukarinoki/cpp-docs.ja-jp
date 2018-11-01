---
title: '方法: 遅延後に完了するタスクを作成する'
ms.date: 11/04/2016
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
ms.openlocfilehash: 89564a00dbfde078ef98cd53110853e30e33ad6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616338"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>方法: 遅延後に完了するタスクを作成する

この例は、使用する方法を示します、 [concurrency::task](../../parallel/concrt/reference/task-class.md)、 [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)、 [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)、 [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)、 [concurrency::timer](../../parallel/concrt/reference/timer-class.md)、および[concurrency::call](../../parallel/concrt/reference/call-class.md)遅延後に完了するタスクを作成するためのクラス。 このメソッドを使用すると、場合によってはデータをポーリング、タイムアウトを導入、あらかじめ決められた期間、ユーザー入力の処理の遅延、具合をループをビルドします。

## <a name="example"></a>例

`complete_after` 関数および `cancel_after_timeout` 関数の例を次に示します。 `complete_after`関数を作成、`task`オブジェクトを指定した遅延後に完了します。 使用して、`timer`オブジェクトと`call`を設定するオブジェクト、`task_completion_event`指定された遅延の後のオブジェクト。 使用して、`task_completion_event`クラス、スレッドの後に完了するタスクを定義することや、別のタスクは使用可能な値を示します。 イベントが設定されている場合は、リスナー タスクが完了し、その継続の実行がスケジュールされています。

> [!TIP]
>  詳細については、`timer`と`call`Asynchronous Agents Library の一部のクラスを参照してください[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。

`cancel_after_timeout`関数に基づいて、`complete_after`そのタスクが指定したタイムアウト時間の前に完了しない場合は、タスクをキャンセルする関数。 `cancel_after_timeout`関数は、2 つのタスクを作成します。 最初のタスクの成功を示すし、指定されたタスクの完了後に完了2 番目のタスクは、エラーを示し、指定したタイムアウト後に完了します。 `cancel_after_timeout`関数が成功または失敗のタスクが完了したときに実行される継続タスクを作成します。 エラー タスクには、最初が完了すると、継続は、全体的なタスクをキャンセルするトークンのソースをキャンセルします。

[!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]

## <a name="example"></a>例

次の例は、[0, 100000] の範囲内の素数の数を計算します。 複数回です。 指定された時間制限内に完了しない場合、操作が失敗します。 `count_primes`関数が使用する方法を示します、`cancel_after_timeout`関数。 特定の範囲内の素数の数をカウントし、指定された時間内にタスクが完了しない場合は失敗します。 `wmain`関数呼び出し、`count_primes`複数回に機能します。 常に、制限時間は半分です。 プログラムの完了後、現在の制限時間内に操作が完了しません。

[!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]

この手法を使用して遅延後にタスクをキャンセルするときにタスク全体が取り消された後、まだ開始していないタスクは開始されません。 ただし、適切なタイミングで、キャンセルに応答する、実行時間の長いタスクの重要なは。 タスクのキャンセルの詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)します。

## <a name="example"></a>例

この例の完全なコードを次に示します。

[!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするにコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`task-delay.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc タスク-delay.cpp**

## <a name="see-also"></a>関連項目

[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[task クラス (コンカレンシー ランタイム)](../../parallel/concrt/reference/task-class.md)<br/>
[cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)<br/>
[cancellation_token クラス](../../parallel/concrt/reference/cancellation-token-class.md)<br/>
[task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)<br/>
[timer クラス](../../parallel/concrt/reference/timer-class.md)<br/>
[call クラス](../../parallel/concrt/reference/call-class.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)

