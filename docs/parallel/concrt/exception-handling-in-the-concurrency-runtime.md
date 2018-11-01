---
title: コンカレンシー ランタイムでの例外処理
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks, exception handling [Concurrency Runtime]
- exception handling [Concurrency Runtime]
- structured task groups, exception handling [Concurrency Runtime]
- agents, exception handling [Concurrency Runtime]
- task groups, exception handling [Concurrency Runtime]
ms.assetid: 4d1494fb-3089-4f4b-8cfb-712aa67d7a7a
ms.openlocfilehash: 7611e9d3f0bbf961784c9fed23117750a101486f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50437870"
---
# <a name="exception-handling-in-the-concurrency-runtime"></a>コンカレンシー ランタイムでの例外処理

コンカレンシー ランタイムは、C++ 例外処理を使用してさまざまなエラーを通知します。 そのエラーには、ランタイムの不適切な使用、リソースの取得の失敗などのランタイム エラー、タスクおよびタスク グループに提供した処理関数で生じるエラーなどがあります。 タスクまたはタスク グループによって例外がスローされると、ランタイムはその例外を保持し、タスクまたはタスク グループの完了を待機するコンテキストにマーシャリングします。 軽量タスクやエージェントなどのコンポーネントの例外は、ランタイムによって自動的には管理されません。 そのため、独自の例外処理機構を実装する必要があります。 このトピックでは、タスク、タスク グループ、軽量タスク、および非同期エージェントによってスローされた例外をランタイムが処理するしくみと、アプリケーションで例外に応答する方法を説明します。

## <a name="key-points"></a>主要なポイント

- タスクまたはタスク グループによって例外がスローされると、ランタイムはその例外を保持し、タスクまたはタスク グループの完了を待機するコンテキストにマーシャリングします。

- 可能であれば、すべての呼び出しを囲む[::task_canceled](reference/task-class.md#get)と[::wait](reference/task-class.md#wait)で、 `try` / `catch`回復できるエラーを処理するためにブロック差出人。 タスクが例外をスローし、その例外がそのタスク、その継続の 1 つ、またはメイン アプリケーションによってキャッチされない場合、ランタイムはアプリケーションを終了します。

- タスク ベースの継続は常に実行されます。継続元タスクが正常に完了したかどうか、例外をスローしたかどうか、または取り消されたかどうかは、関係ありません。 値ベースの継続は、継続元タスクがスローまたは取り消すと、実行されません。

- タスク ベースの継続は常に実行されるため、継続チェーンの末尾にタスク ベースの継続を追加することを検討してください。 これにより、コードですべての例外が確認されることを保証できます。

- ランタイムによってスロー [concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md)を呼び出すと[::task_canceled](reference/task-class.md#get)され、そのタスクが取り消されます。

- ランタイムは、軽量タスクと軽量エージェントの例外を管理しません。

##  <a name="top"></a> このドキュメントで

- [タスクおよび継続](#tasks)

- [タスク グループと並列アルゴリズム](#task_groups)

- [ランタイムによってスローされた例外](#runtime)

- [複数の例外](#multiple)

- [キャンセル](#cancellation)

- [軽量タスク](#lwts)

- [非同期エージェント](#agents)

##  <a name="tasks"></a> タスクおよび継続

このセクションでは、によってスローされる例外をランタイムが処理する方法について説明します[concurrency::task](../../parallel/concrt/reference/task-class.md)オブジェクトおよびその継続します。 タスクおよび継続モデルの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。

渡す処理関数の本体で例外をスローするときに、`task`オブジェクト、ランタイムはその例外を保存し、呼び出すコンテキストにマーシャ リング[::task_canceled](reference/task-class.md#get)または[同時実行。task::wait](reference/task-class.md#wait)します。 ドキュメント[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)について説明します値ベースの継続が要約すると、値ベースの継続とタスク ベースの型のパラメーターを受け取る`T`とタスク ベースの継続は、型のパラメーターを受け取る`task<T>`. スローするタスクに 1 つ以上の値ベースの継続がある場合、それらの継続を実行するスケジュールは設定されません。 この動作を次の例に示します。

[!code-cpp[concrt-eh-task#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_1.cpp)]

タスク ベースの継続では、継続元タスクによってスローされるすべての例外を処理することができます。 タスク ベースの継続は常に実行されます。そのタスクが正常に完了したかどうか、例外をスローしたかどうか、または取り消されたかどうかは、関係ありません。 タスクが例外をスローする場合、タスク ベースの継続を実行するようにスケジュールが設定されます。 次の例は、常にスローするタスクを示しています。 タスクには 2 つの継続があります。1 つが値ベースで他方がタスク ベースです。 タスク ベースの例外は、常に実行されるため、継続元タスクによってスローされる例外をキャッチすることができます。 `task::get` または `task::wait` が呼び出されると、タスクの例外が常にスローされます。そのため、例が両方の継続の完了を待機しているときに、例外が再度スローされます。

[!code-cpp[concrt-eh-continuations#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_2.cpp)]

処理できる例外をキャッチするために、タスク ベースの継続を使用することをお勧めします。 タスク ベースの継続は常に実行されるため、継続チェーンの末尾にタスク ベースの継続を追加することを検討してください。 これにより、コードですべての例外が確認されることを保証できます。 次の例は、基本的な値ベースの継続チェーンを示しています。 このチェーン スローの 3 番目のタスクおよび後続の値ベースの継続は、実行されません。 ただし、最後の継続は、タスク ベースであるため常に実行されます。 この最後の継続は、3 番目のタスクによってスローされる例外を処理します。

できるだけ具体性の高い例外をキャッチすることをお勧めします。 キャッチする具体的な例外がない場合は、この最後のタスク ベースの継続を省略できます。 この場合、すべての例外が未処理になり、アプリケーションが停止する可能性があります。

[!code-cpp[concrt-eh-task-chain#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_3.cpp)]

> [!TIP]
>  使用することができます、 [::task_completion_event::set_exception](../../parallel/concrt/reference/task-completion-event-class.md)タスクの完了イベントと例外を関連付けるメソッド。 ドキュメント[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)について説明します、 [concurrency::task_completion_event](../../parallel/concrt/reference/task-completion-event-class.md)クラスがさらに詳しく説明します。

[concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md)に関連する重要なランタイム例外の種類は、`task`します。 `task_canceled` が呼び出され、そのタスクが取り消された場合、ランライムは `task::get` をスローします (逆に、`task::wait`返します[task_status](reference/concurrency-namespace-enums.md#task_group_status)スローしません)。タスク ベースの継続から、この例外をキャッチして処理できます。または、`task::get` を呼び出すと、この例外をキャッチして処理できます。 タスクのキャンセルの詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)します。

> [!CAUTION]
>  コードから `task_canceled` をスローしないでください。 呼び出す[concurrency::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task)代わりにします。

タスクが例外をスローし、その例外がそのタスク、その継続の 1 つ、またはメイン アプリケーションによってキャッチされない場合、ランタイムはアプリケーションを終了します。 アプリケーションがクラッシュした場合、C++ の例外がスローされると中断するように Visual Studio を構成できます。 未処理の例外の場所を診断したら、タスク ベースの継続を使用してそれを処理します。

セクション[ランタイムによって例外がスロー](#runtime)このドキュメントでさらに詳しく例外をランタイムを使用する方法について説明します。

[[トップ](#top)]

##  <a name="task_groups"></a> タスク グループと並列アルゴリズム

ここでは、タスク グループによってスローされた例外をランタイムが処理するしくみについて説明します。 このセクションにも当てはまります並列アルゴリズムなど[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)タスク グループにこれらのアルゴリズムが構築されるため、します。

> [!CAUTION]
>  例外が依存タスクに及ぼす影響を十分に理解しておいてください。 例外処理タスクまたは並列アルゴリズムを使用する方法について推奨されるプラクティスについては、次を参照してください、[理解する方法のキャンセル機能と例外は、オブジェクトの破棄を影響を与える処理](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction)、並列でのベスト プラクティス」セクション。パターン ライブラリのトピックです。

タスク グループの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。 並列アルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。

渡す処理関数の本体で例外をスローするときに、 [concurrency::task_group](reference/task-group-class.md)または[concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)オブジェクト、ランタイムはその例外を保存し、マーシャ リング呼び出すコンテキストに[::task_group::wait](reference/task-group-class.md#wait)、 [concurrency::structured_task_group::wait](reference/structured-task-group-class.md#wait)、 [concurrency::task_group::run_and_wait](reference/task-group-class.md#run_and_wait)、または[::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait)します。 また、ランタイムは、タスク グループ内のすべてのアクティブ タスク (子タスク グループ内のタスクも含む) を中止すると共に、開始されていないすべてのタスクを破棄します。

次の例は、例外をスローする処理関数の基本的な構造を示しています。 この例では、`task_group` オブジェクトを使用して 2 つの `point` オブジェクトの値を並列的に出力します。 `print_point` 処理関数は `point` オブジェクトの値をコンソールに出力します。 入力値が `NULL` の場合、処理関数は例外をスローします。 ランタイムはこの例外を保存し、`task_group::wait` を呼び出すコンテキストにその例外をマーシャリングします。

[!code-cpp[concrt-eh-task-group#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_4.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
X = 15, Y = 30Caught exception: point is NULL.
```

タスク グループでの例外処理を使用する完全な例を参照してください。[方法: 例外処理を使用して中断する並列ループから](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)します。

[[トップ](#top)]

##  <a name="runtime"></a> ランタイムによってスローされた例外

ランタイムの呼び出しから例外が発生する可能性があります。 ほとんどの種類の例外を除き[concurrency::task_canceled](../../parallel/concrt/reference/task-canceled-class.md)と[concurrency::operation_timed_out](../../parallel/concrt/reference/operation-timed-out-class.md)、プログラミング エラーを示します。 一般にこれらのエラーは回復不能であるため、アプリケーション コードではキャッチまたは処理できません。 プログラミング エラーを診断する必要がある場合にのみ、回復不能なエラーをアプリケーション コードでキャッチまたは処理することをお勧めします。 ただし、ランタイムで定義されている例外の種類を把握しておけば、プログラミング エラーを診断するときに役立ちます。

ランタイムによってスローされる例外の例外処理機構は、処理関数によってスローされる例外の例外処理機構と同じです。 たとえば、 [concurrency::receive](reference/concurrency-namespace-functions.md#receive)関数がスロー`operation_timed_out`ときを受け取らず、メッセージで指定された期間。 タスク グループに渡す処理関数で `receive` が例外をスローすると、ランタイムはその例外を保存して、`task_group::wait`、`structured_task_group::wait`、`task_group::run_and_wait`、または `structured_task_group::run_and_wait` を呼び出すコンテキストにその例外をマーシャリングします。

次の例では、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムを並列で 2 つのタスクを実行します。 1 つ目のタスクは 5 秒間待機した後、メッセージをメッセージ バッファーに送信します。 2 つ目のタスクは `receive` 関数を使用して 3 秒間待機し、同じメッセージ バッファーからメッセージを受信します。 `receive` 関数は、時間内にメッセージを受信しなかった場合、`operation_timed_out` をスローします。

[!code-cpp[concrt-eh-time-out#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_5.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
The operation timed out.
```

アプリケーションの異常終了を防ぐために、コードでランタイムを呼び出す場合は例外が処理されるようにしてください。 また、サードパーティのライブラリなど、コンカレンシー ランタイムを使用する外部コードを呼び出す場合にも、例外を処理する必要があります。

[[トップ](#top)]

##  <a name="multiple"></a> 複数の例外

タスクまたは並列アルゴリズムが複数の例外を受け取った場合、ランタイムはそのいずれか 1 つだけを呼び出し元のコンテキストにマーシャリングします。 どの例外がマーシャリングされるかは、任意です。

次の例では、`parallel_for` アルゴリズムを使用して、数値をコンソールに出力します。 入力値が指定の最小値未満であるか、最大値を超えている場合、例外がスローされます。 この例では、複数の処理関数が例外をスローする可能性があります。

[!code-cpp[concrt-eh-multiple#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_6.cpp)]

この例のサンプル出力を次に示します。

```Output
8293104567Caught exception: -5: the value is less than the minimum.
```

[[トップ](#top)]

##  <a name="cancellation"></a> キャンセル

すべての例外がエラーの存在を示すわけではありません。 たとえば、検索アルゴリズムは結果を検出したときに、例外処理を使用して、関連付けられているタスクを中止することがあります。 コードで取り消しの機構を使用する方法の詳細については、次を参照してください。 [PPL における取り消し処理](../../parallel/concrt/cancellation-in-the-ppl.md)します。

[[トップ](#top)]

##  <a name="lwts"></a> 軽量タスク

軽量タスクから直接スケジュールしたタスク、 [concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)オブジェクト。 軽量タスクは、通常のタスクよりもオーバーヘッドが小さくなります。 ただし、ランタイムは軽量タスクによってスローされた例外をキャッチしません。 代わりに、ハンドルされない例外のハンドラーが例外をキャッチし、既定ではプロセスを終了します。 したがって、アプリケーションで適切なエラー処理機構を使用する必要があります。 軽量タスクの詳細については、次を参照してください。[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。

[[トップ](#top)]

##  <a name="agents"></a> 非同期エージェント

軽量タスクと同様に、ランタイムは非同期エージェントによってスローされた例外を管理しません。

次の例から派生したクラスで例外を処理する方法の 1 つ[concurrency::agent](../../parallel/concrt/reference/agent-class.md)します。 この例では、`points_agent` クラスを定義しています。 `points_agent::run` メソッドはメッセージ バッファーから `point` オブジェクトを読み取り、それをコンソールに出力します。 `run` メソッドは、`NULL` ポインターを受け取った場合に例外をスローします。

`run`メソッドは、すべての処理を囲む、 `try` - `catch`ブロックします。 `catch` ブロックは、例外をメッセージ バッファーに格納します。 アプリケーションは、エージェントの終了後にこのバッファーから例外を読み取ることで、エージェントでのエラーの有無をチェックします。

[!code-cpp[concrt-eh-agents#1](../../parallel/concrt/codesnippet/cpp/exception-handling-in-the-concurrency-runtime_7.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
X: 10 Y: 20
X: 20 Y: 30
error occurred in agent: point must not be NULL
the status of the agent is: done
```

`try` - `catch`外部ブロックが存在する、`while`ループ、エージェントの終了が最初のエラーが発生したときに処理します。 場合、 `try` - `catch`ブロックが内、`while`ループ、エラーが発生した後、エージェントを引き続きとします。

この例では例外がメッセージ バッファーに格納されるため、別のコンポーネントが実行中のエージェントのエラーを監視できます。 この例では、 [concurrency::single_assignment](../../parallel/concrt/reference/single-assignment-class.md)エラーを格納するオブジェクト。 エージェントが複数の例外を処理する場合、`single_assignment` クラスは渡された最初のメッセージだけを保存します。 最後の例外だけを保存するには、使用、 [concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)クラス。 すべての例外を保存するには、使用、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)クラス。 これらのメッセージ ブロックの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。

非同期エージェントの詳細については、次を参照してください。[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)します。

[[トップ](#top)]

##  <a name="summary"></a> まとめ

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイム](../../parallel/concrt/concurrency-runtime.md)<br/>
[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

