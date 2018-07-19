---
title: '方法: 遅延後に完了するタスクを作成 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- task_completion_event class, example
- create a task that completes after a delay, example [C++]
ms.assetid: 3fc0a194-3fdb-4eba-8b8a-b890981a985d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fca1ba3874f02b44f96fd795b531536a23c8d462
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688412"
---
# <a name="how-to-create-a-task-that-completes-after-a-delay"></a>方法: 遅延後に完了するタスクを作成する
この例を使用する方法を示しています、 [concurrency::task](../../parallel/concrt/reference/task-class.md)、 [concurrency::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)、 [concurrency::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)、 [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)、 [concurrency::timer](../../parallel/concrt/reference/timer-class.md)、および[concurrency::call](../../parallel/concrt/reference/call-class.md)遅延後に完了するタスクを作成するクラス。 このメソッドは、ループをときどきデータをポーリングのタイムアウトを導入、あらかじめ決められた時間は、ユーザー入力の処理を遅延に表示され、ビルドを使用することができます。  
  
## <a name="example"></a>例  
 `complete_after` 関数および `cancel_after_timeout` 関数の例を次に示します。 `complete_after`関数を作成、`task`オブジェクトを指定した遅延後に完了します。 使用して、`timer`オブジェクトおよび`call`を設定するオブジェクト、`task_completion_event`経過すると、指定したオブジェクト。 使用して、`task_completion_event`クラス、スレッドの後に完了するタスクを定義することや、別のタスクは、値が使用できることを通知します。 イベントが設定されている場合は、リスナー タスクが完了し、その継続の実行がスケジュールされています。  
  
> [!TIP]
>  詳細については、`timer`と`call`非同期エージェント ライブラリの一部のクラスを参照してください[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
 `cancel_after_timeout`関数に基づいて、`complete_after`関数を指定したタイムアウト時間の前にそのタスクが完了しない場合は、タスクを取り消します。 `cancel_after_timeout`関数は 2 つのタスクを作成します。 最初のタスクの成功を示し、指定されたタスクの完了後に完了2 番目のタスクは、失敗を示し、指定されたタイムアウトの後に完了します。 `cancel_after_timeout`関数が成功または失敗のタスクが完了したときに実行される継続タスクを作成します。 エラー タスクが最初に完了する場合、継続は、全体的なタスクを取り消すには、トークンのソースをキャンセルします。  
  
 [!code-cpp[concrt-task-delay#1](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_1.cpp)]  
  
## <a name="example"></a>例  
 次の例は、[0, 100000] の範囲に含まれる素数の数を計算複数回です。 指定された制限時間内に完了しない場合、操作が失敗します。 `count_primes`関数を使用する方法を示しています、`cancel_after_timeout`関数。 特定の範囲内の素数の数をカウントし、タスクが、指定された時間内に完了しない場合は失敗します。 `wmain`関数呼び出し、`count_primes`複数回に機能します。 常に、制限時間は半分です。 プログラムの完了後、操作が現在の制限時間内に完了しません。  
  
 [!code-cpp[concrt-task-delay#2](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_2.cpp)]  
  
 この手法を使用して遅延後にタスクをキャンセルするときにタスク全体が取り消された後、まだ開始していないタスクは開始されません。 ただし、キャンセルに適時に応答する、実行時間の長いタスクの重要な。 タスクのキャンセルの詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)です。  
  
## <a name="example"></a>例  
 この例の完全なコードを次に示します。  
  
 [!code-cpp[concrt-task-delay#3](../../parallel/concrt/codesnippet/cpp/how-to-create-a-task-that-completes-after-a-delay_3.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`task-delay.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc タスク delay.cpp**  
  
## <a name="see-also"></a>関連項目  
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [task クラス (同時実行ランタイム)](../../parallel/concrt/reference/task-class.md)   
 [cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)   
 [cancellation_token クラス](../../parallel/concrt/reference/cancellation-token-class.md)   
 [task_completion_event クラス](../../parallel/concrt/reference/task-completion-event-class.md)   
 [timer クラス](../../parallel/concrt/reference/timer-class.md)   
 [クラスを呼び出します。](../../parallel/concrt/reference/call-class.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [PPL における取り消し処理](cancellation-in-the-ppl.md)

