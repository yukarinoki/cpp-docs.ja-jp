---
title: PPL における取り消し処理
ms.date: 11/19/2018
helpviewer_keywords:
- parallel algorithms, canceling [Concurrency Runtime]
- canceling parallel algorithms [Concurrency Runtime]
- parallel tasks, canceling [Concurrency Runtime]
- cancellation in the PPL
- parallel work trees [Concurrency Runtime]
- canceling parallel tasks [Concurrency Runtime]
ms.assetid: baaef417-b2f9-470e-b8bd-9ed890725b35
ms.openlocfilehash: 27c0ea3cfcf62060800c1c0b034dde7de6357250
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368492"
---
# <a name="cancellation-in-the-ppl"></a>PPL における取り消し処理

このドキュメントでは、並列パターン ライブラリ (PPL: Parallel Patterns Library) での取り消し処理の役割、並列処理を取り消す方法、および並列処理の取り消しを判定する方法について説明します。

> [!NOTE]
> ランタイムは例外処理を使用して取り消し処理を実装します。 これらの例外をコードでキャッチまたは処理しないでください。 さらに、タスクの関数本体では例外セーフなコードを作成することをお勧めします。 たとえば、*リソース取得の初期化*(RAII) パターンを使用して、タスクの本体で例外がスローされたときにリソースが正しく処理されるようにすることができます。 RAII パターンを使用して取り消し可能なタスクのリソースをクリーンアップする完全な例については、「[チュートリアル: ユーザー インターフェイス スレッドからの作業の削除](../../parallel/concrt/walkthrough-removing-work-from-a-user-interface-thread.md)」を参照してください。

## <a name="key-points"></a>重要なポイント

- 取り消し処理は他の処理と連携して行われ、取り消し処理を要求するコードと取り消し処理に応答するタスクの間に連携が必要です。

- 可能な場合は、キャンセル トークンを使用して処理を取り消します。 [同時実行::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)クラスは、キャンセル トークンを定義します。

- キャンセル トークンを使用する場合は、[同時実行性::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel)メソッドを使用してキャンセルを開始し、[同時実行::cancel_current_task](reference/concurrency-namespace-functions.md#cancel_current_task)関数を使用してキャンセルに応答します。 他のタスクがキャンセルを要求したかどうかを確認するには[、同時実行:cancellation_token::is_canceled](reference/cancellation-token-class.md#is_canceled)メソッドを使用します。

- 取り消し処理はすぐに実行されません。 タスクまたはタスク グループが取り消された場合、新しい作業は開始されませんが、アクティブな作業は取り消しを確認して応答する必要があります。

- 値ベースの継続は、継続元タスクのキャンセル トークンを継承します。 タスク ベースの継続は、継続元タスクのトークンを継承しません。

- `cancellation_token`オブジェクトを受け取るコンストラクタまたは関数を呼び出すが、操作を取り消し可能にしたくない場合は、[並行性::cancellation_token::none](reference/cancellation-token-class.md#none)メソッドを使用します。 また、[同時実行性::task](../../parallel/concrt/reference/task-class.md)コンストラクタまたは[同時実行::create_task](reference/concurrency-namespace-functions.md#create_task)関数にキャンセルトークンを渡さない場合、そのタスクは取り消しできません。

## <a name="in-this-document"></a><a name="top"></a>このドキュメントでは

- [並列処理ツリー](#trees)

- [並列タスクの取り消し](#tasks)

  - [キャンセル トークンを使用して並列処理を取り消す](#tokens)

  - [cancel メソッドを使用した並列処理の取り消し](#cancel)

  - [例外を使用した並列処理の取り消し](#exceptions)

- [並列アルゴリズムの取り消し](#algorithms)

- [取り消し処理が適さないケース](#when)

## <a name="parallel-work-trees"></a><a name="trees"></a>並列作業ツリー

PPL は、細かく分類されたタスクおよび計算を管理するためにタスクとタスク グループを使用します。 タスク グループをネストして、並列作業の*ツリー*を形成できます。 並列処理ツリーの図を次に示します。 この図では、`tg1` と `tg2` はタスク グループを表し、`t1`、`t2`、`t3`、`t4`、および `t5` はタスク グループによって実行される処理を表しています。

![並列処理ツリー](../../parallel/concrt/media/parallelwork_trees.png "並列処理ツリー")

前の図のツリーを作成するために必要なコード例を次に示します。 この例では、`tg1``tg2`[同時実行性::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)オブジェクトです。`t1`、 `t2` `t3`、 `t4`、 `t5` 、およびは[同時実行です::task_handle](../../parallel/concrt/reference/task-handle-class.md)オブジェクトです。

[!code-cpp[concrt-task-tree#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_1.cpp)]

[同時実行::task_group](reference/task-group-class.md)クラスを使用して、同様の作業ツリーを作成することもできます。 [同時実行::タスク](../../parallel/concrt/reference/task-class.md)クラスは、作業ツリーの概念もサポートします。 ただし、`task` ツリーは依存ツリーです。 `task` ツリーでは、将来の処理は現在の処理の後に完了します。 タスク グループ ツリーでは、内部処理は外部処理の前に完了します。 タスクとタスク グループの違いの詳細については、「[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)」を参照してください。

[[トップ](#top)]

## <a name="canceling-parallel-tasks"></a><a name="tasks"></a>並列タスクの取り消し

並列処理を取り消すには複数の方法があります。 推奨する方法は、キャンセル トークンを使用する方法です。 タスク グループは[、同時実行性::task_group::キャンセル](reference/task-group-class.md#cancel)メソッドと[同時実行::structured_task_group::cancel](reference/structured-task-group-class.md#cancel)メソッドもサポートしています。 最後の方法は、タスクの処理関数の本体で例外をスローする方法です。 どの方法を選択した場合でも、取り消し処理はすぐに実行されません。 タスクまたはタスク グループが取り消された場合、新しい作業は開始されませんが、アクティブな作業は取り消しを確認して応答する必要があります。

並列タスクを取り消すその他の例については、「[チュートリアル: タスクと XML HTTP 要求を使用した接続](../../parallel/concrt/walkthrough-connecting-using-tasks-and-xml-http-requests.md)、[方法: キャンセルを使用して並列ループから切り離](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)す」、および「[方法: 例外処理を使用して並列ループから切り離す](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)」を参照してください。

### <a name="using-a-cancellation-token-to-cancel-parallel-work"></a><a name="tokens"></a>キャンセル トークンを使用した並列作業の取り消し

`task`、`task_group`、および `structured_task_group` の各クラスでは、キャンセル トークンを使用した取り消し処理をサポートしています。 PPL は、この目的のために[同時実行性::cancellation_token_source](../../parallel/concrt/reference/cancellation-token-source-class.md)と[同時実行::cancellation_token](../../parallel/concrt/reference/cancellation-token-class.md)クラスを定義します。 作業を取り消すためにキャンセル トークンを使用すると、ランタイムはそのトークンをサブスクライブする新しい作業を開始しません。 既にアクティブになっている作業では[、is_canceled](../../parallel/concrt/reference/cancellation-token-class.md#is_canceled)メンバー関数を使用してキャンセル トークンを監視し、可能な場合は停止できます。

キャンセルを開始するには、同時実行を呼び出します[::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel)メソッドです。 次の方法で取り消し処理に応答します。

- オブジェクト`task`の場合は、[同時実行::cancel_current_task関数を](reference/concurrency-namespace-functions.md#cancel_current_task)使用します。 `cancel_current_task` が現在のタスクとすべての値ベースの継続を取り消します (タスクまたはその継続に関連付けられているキャンセル*トークン*は取り消されません)。

- タスク グループと並列アルゴリズムの場合は、[同時実行を検出するために、同時実行::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling)関数を使用し、この関数が**true**を返すときにタスク本体からできるだけ早く返します。 (タスク グループから `cancel_current_task` を呼び出さないでください)。

次の例では、タスク取り消し処理の最初の基本的なパターンを示しています。 タスクの本体は、ループ内の取り消し状態を適宜チェックします。

[!code-cpp[concrt-task-basic-cancellation#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_2.cpp)]

`cancel_current_task` 関数がスローします。したがって、現在のループまたは関数から明示的に戻る必要はありません。

> [!TIP]
> または、[並行性::interruption_point](reference/concurrency-namespace-functions.md#interruption_point)関数を`cancel_current_task`呼び出すことができます。

取り消し処理に応答するときは `cancel_current_task` を呼び出すことが重要です。この関数によって、タスクが取り消し状態に遷移します。 `cancel_current_task` を呼び出さずに早期に戻った場合、操作は完了状態に遷移し、すべての値ベースの継続が実行されます。

> [!CAUTION]
> コードから `task_canceled` をスローしないでください。 代わりに `cancel_current_task` を呼び出してください。

タスクが取り消された状態で終了すると、[同時実行::task::get](reference/task-class.md#get)メソッドは[同時実行をスローします::task_canceled.](../../parallel/concrt/reference/task-canceled-class.md) (逆に、[同時実行::タスク::待機](reference/task-class.md#wait)は[task_status::キャンセルされ](reference/concurrency-namespace-enums.md#task_group_status)、スローされません。次の例は、タスクベースの継続に対するこの動作を示しています。 タスク ベースの継続は、その継続元タスクが取り消された場合でも必ず呼び出されます。

[!code-cpp[concrt-task-canceled#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_3.cpp)]

値ベースの継続は、明示的なトークンで作成された場合を除き、継続元タスクのトークンを継承するため、継続元タスクがまだ実行中の場合でも、すぐに取り消し状態になります。 したがって、取り消し後に継続元タスクによってスローされた例外は、継続タスクに反映されません。 取り消し処理によって、継続元タスクの状態は常にオーバーライドされます。 次の例は、前の例に似ていますが、値ベースの継続の動作を示しています。

[!code-cpp[concrt-task-canceled#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_4.cpp)]

> [!CAUTION]
> コンストラクタまたは[同時実行::create_task](reference/concurrency-namespace-functions.md#create_task)関数にキャンセル`task`トークンを渡さない場合、そのタスクはキャンセルできません。 また、入れ子のタスク (別のタスクの本体で作成されたタスク) のコンストラクターに同じキャンセル トークンを渡して、すべてのタスクを同時に取り消す必要があります。

キャンセル トークンが取り消されるときに任意のコードを実行できます。 たとえば、ユーザーインターフェイスで **[キャンセル]** ボタンをクリックして操作をキャンセルした場合、ユーザーが別の操作を開始するまで、そのボタンを無効にできます。 次の例では、同時実行を使用する方法を示しています[、::cancellation_token:register_callback](reference/cancellation-token-class.md#register_callback)メソッドは、キャンセルトークンがキャンセルされたときに実行されるコールバック関数を登録します。

[!code-cpp[concrt-task-cancellation-callback#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_5.cpp)]

ドキュメント[タスク並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)では、値ベースとタスクベースの継続の違いを説明します。 継続タスクに `cancellation_token` オブジェクトを提供しない場合、継続はキャンセル トークンを継続元タスクから次のように継承します。

- 値ベースの継続は、継続元タスクのキャンセル トークンを必ず継承します。

- タスク ベースの継続は、継続元タスクのキャンセル トークンを継承しません。 タスク ベースの継続を取り消し可能にする唯一の方法は、明示的にキャンセル トークンを渡すことです。

これらの動作は、違反になったタスク (つまり、例外をスローするタスク) の影響を受けません。 この場合、値ベースの継続は取り消されます。タスクベースの継続は取り消されません。

> [!CAUTION]
> 別のタスクに作成されているタスク (つまり、入れ子のタスク) は、親タスクのキャンセル トークンを継承しません。 値ベースの継続のみ、継続元タスクのキャンセル トークンを継承します。

> [!TIP]
> オブジェクトを受け取るコンストラクターまたは関数を呼び出し、操作を取り消し可能にしたくない場合は、[同時実行 cancellation_tokenを](reference/cancellation-token-class.md#none)使用します。 `cancellation_token`

また、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのコンストラクターにキャンセル トークンを指定できます。 このとき重要な点は、子タスク グループがこのキャンセル トークンを継承することです。 この概念を示す例については、[並列実行::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token)関数を使用して呼び出`parallel_for`すを[Canceling Parallel Algorithms](#algorithms)呼び出します。

[[トップ](#top)]

#### <a name="cancellation-tokens-and-task-composition"></a>キャンセル トークンとタスク構成

[同時実行::when_all](reference/concurrency-namespace-functions.md#when_all)と[同時実行:when_any](reference/concurrency-namespace-functions.md#when_all)関数は、共通のパターンを実装するために複数のタスクを作成するのに役立ちます。 このセクションでは、キャンセル トークンを使用した場合のこれらの関数の動作について説明します。

関数に`when_all``when_any`キャンセル トークンを提供すると、そのキャンセル トークンがキャンセルされた場合、または参加タスクの 1 つがキャンセル状態で終了するか、例外がスローされた場合にのみ、その関数がキャンセルされます。

`when_all` 関数にキャンセル トークンを指定していない場合、この関数は、操作全体を構成する各タスクからキャンセル トークンを継承します。 返されるタスク`when_all`は、これらのトークンのいずれかが取り消され、少なくとも 1 つの参加者タスクがまだ開始されていないか、実行中である場合に取り消されます。 同様の動作は、タスクの 1 つが例外をスローしたときに発生します。 `when_all`

ランタイムは、タスクが完了したときに `when_any` 関数から返されるタスクのキャンセル トークンを選択します。 完了状態になった参加タスクがなく、1 つまたは複数のタスクが例外をスローした場合、スローしたタスクの 1 つが `when_any` を完了するために選択され、そのトークンが最後のタスクのトークンとして選択されます。 複数のタスクが完了状態になった場合、`when_any` タスクから返されるタスクは、完了状態になります。 ランタイムは、他の実行中のタスクが後で完了する可能性がある場合でも、`when_any` から返されるタスクがすぐに取り消されないように、完了時にトークンが取り消されていない完了したタスクを選択しようとします。

[[トップ](#top)]

### <a name="using-the-cancel-method-to-cancel-parallel-work"></a><a name="cancel"></a>キャンセルメソッドを使用した並列作業のキャンセル

[同時実行::task_group::キャンセル](reference/task-group-class.md#cancel)と[同時実行::structured_task_group::キャンセル](reference/structured-task-group-class.md#cancel)メソッドは、タスク グループをキャンセルされた状態に設定します。 `cancel` を呼び出すと、それ以降はタスク グループでタスクが開始されなくなります。 `cancel` メソッドは、複数の子タスクから呼び出すことができます。 キャンセルされたタスクは[、同時実行制御を返すために同時実行を引き起こします::task_group::待機](reference/task-group-class.md#wait)と[同時実行::structured_task_group::wait](reference/structured-task-group-class.md#wait)メソッド[は、同時実行を返します::キャンセル.](reference/concurrency-namespace-enums.md#task_group_status)

タスク グループが取り消されると、各子タスクからランタイムへの呼び出しによって*中断ポイント*がトリガーされ、ランタイムがスローし、アクティブなタスクをキャンセルする内部例外の種類をキャッチします。 コンカレンシー ランタイムでは、特定の割り込みポイントが定義されていません。割り込みポイントは、ランタイムに対する任意の呼び出しで発生します。 ランタイムは、取り消し処理を実行するために、自身がスローした例外を処理する必要があります。 このため、タスクの本体で不明な例外を処理しないでください。

子タスクが時間のかかる処理を実行しており、ランタイムの呼び出しを行わない場合、子タスクは定期的に取り消し状態をチェックして、適切なタイミングで終了する必要があります。 処理の取り消し状態を判定する方法の 1 つを次の例に示します。 タスク `t4` は、エラーの発生時に親タスク グループを取り消します。 タスク `t5` は、`structured_task_group::is_canceling` メソッドを定期的に呼び出して、取り消し状態をチェックします。 親タスク グループが取り消されると、タスク `t5` はメッセージを表示して終了します。

[!code-cpp[concrt-task-tree#6](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_6.cpp)]

この例では、タスク ループの 100<sup>回目</sup>の反復処理ごとに取り消しをチェックします。 取り消し状態をチェックする頻度は、タスクで実行される処理の量と、取り消し処理にタスクがどの程度すばやく応答する必要があるのかによって決まります。

親タスク グループ オブジェクトへのアクセス権がない場合は、[同時実行::is_current_task_group_canceling](reference/concurrency-namespace-functions.md#is_current_task_group_canceling)関数を呼び出して、親タスク グループが取り消されたかどうかを確認します。

`cancel` メソッドは、子タスクにのみ影響を及ぼします。 たとえば、並列処理ツリーの図のタスク グループ `tg1` を取り消すと、ツリー内のすべてのタスク (`t1`、`t2`、`t3`、`t4`、および `t5`) が取り消されます。 入れ子になったタスク グループ `tg2` を取り消すと、タスク `t4` および `t5` のみ影響を受けます。

`cancel` メソッドを呼び出すと、子タスク グループもすべて取り消されます。 しかし、取り消し処理は、並列処理ツリーにおけるタスク グループの親には影響しません。 以降の例では、並列処理ツリーの図に基づいてこのことを示します。

最初の例では、タスク グループ `t4` の子であるタスク `tg2` の処理関数を作成します。 この処理関数は、関数 `work` をループ内で呼び出します。 `work` の呼び出しが失敗すると、タスクは親タスク グループを取り消します。 これにより、タスク グループ `tg2` が取り消された状態になりますが、タスク グループ `tg1` は取り消されません。

[!code-cpp[concrt-task-tree#2](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_7.cpp)]

次の例は、最初の例と似ていますが、タスクがタスク グループ `tg1` を取り消す点が異なっています。 これにより、ツリー内のすべてのタスク (`t1`、`t2`、`t3`、`t4`、および `t5`) が影響を受けます。

[!code-cpp[concrt-task-tree#3](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_8.cpp)]

`structured_task_group` クラスはスレッドセーフではありません。 したがって、子タスクが親 `structured_task_group` オブジェクトのメソッドを呼び出すと、未定義の動作が実行されます。 この規則の例外は`structured_task_group::cancel`、 と[同時実行::structured_task_group:is_canceling](reference/structured-task-group-class.md#is_canceling)メソッドです。 子タスクがこれらのメソッドを呼び出すことで、親タスク グループを取り消したり、取り消し状態をチェックしたりできます。

> [!CAUTION]
> `task` オブジェクトの子として実行するタスク グループによって実行される処理を取り消すためにキャンセル トークンを使用できますが、タスク グループで実行する `task_group::cancel` オブジェクトを取り消すために `structured_task_group::cancel` メソッドまたは `task` メソッドは使用できません。

[[トップ](#top)]

### <a name="using-exceptions-to-cancel-parallel-work"></a><a name="exceptions"></a>例外を使用した並列処理の取り消し

並列処理ツリーを取り消す場合は、例外処理を行うよりもキャンセル トークンと `cancel` メソッドを使用する方が効率的です。 キャンセル トークンと `cancel` メソッドは、タスクとすべての子タスクを上位から順に取り消します。 反対に、例外処理では下位から順に処理されるため、例外が上位へ移動するたびに、子タスク グループを個別に取り消す必要があります。 「[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)」では、同時実行ランタイムが例外を使用してエラーを伝える方法について説明します。 しかし、すべての例外がエラーの発生を示す訳ではありません。 たとえば、検索アルゴリズムでは、結果の検出時に関連付けられたタスクが取り消される場合があります。 しかし、前述したように、並列処理の取り消しを行う場合、例外処理は `cancel` メソッドを使用するよりも効率の点で劣ります。

> [!CAUTION]
> 必要なときにだけを並列処理を取り消すために例外を使用することをお勧めします。 キャンセル トークンとタスク グループの `cancel` メソッドの方が効率的で、エラーが発生する可能性も低くなります。

タスク グループに渡す処理関数の本体で例外をスローすると、ランタイムはその例外を保存して、タスク グループの終了を待機するコンテキストにその例外をマーシャリングします。 `cancel` メソッドの場合と同様に、ランタイムはまだ開始されていないタスクを破棄し、新しいタスクを受け付けません。

次の 3 つ目の例は、2 つ目の例と似ていますが、タスク `t4` が例外をスローすることでタスク グループ `tg2` を取り消している点が異なります。 この例では、`try`-`catch`タスク グループ`tg2`が子タスクの終了を待機する際に、ブロックを使用してキャンセルをチェックします。 最初の例と同様に、これによってタスク グループ `tg2` が取り消された状態になりますが、タスク グループ `tg1` は取り消されません。

[!code-cpp[concrt-task-tree#4](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_9.cpp)]

次の 4 つ目の例では、例外処理を使用して処理ツリー全体を取り消します。 この例では、タスク グループ `tg1` が子タスクの終了を待機しているときではなく、タスク グループ `tg2` が子タスクの終了を待機しているときに、例外をキャッチします。 2 番目の例と同様に、これによってツリー内の 2 つのタスク グループ `tg1` および `tg2` の両方が取り消された状態になります。

[!code-cpp[concrt-task-tree#5](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_10.cpp)]

`task_group::wait` メソッドと `structured_task_group::wait` メソッドは、子タスクが例外をスローしたときに実行されるため、これらのメソッドから戻り値を受け取ることはありません。

[[トップ](#top)]

## <a name="canceling-parallel-algorithms"></a><a name="algorithms"></a>並列アルゴリズムのキャンセル

PPL の並列アルゴリズム (`parallel_for` など) は、タスク グループを基準として構築されています。 このため、これまで説明した方法のうちの多くを使用して、並列アルゴリズムを取り消すことができます。

以降の例では、並列アルゴリズムを取り消すためのいくつかの方法を示します。

`run_with_cancellation_token` 関数を使用して `parallel_for` アルゴリズムを呼び出す例を次に示します。 `run_with_cancellation_token` 関数は、引数としてキャンセル トークンを受け取り、指定された処理関数を同期的に呼び出します。 並列アルゴリズムはタスクに基づいて構築されるため、親タスクのキャンセル トークンを継承します。 したがって、`parallel_for` は取り消し処理に応答できます。

[!code-cpp[concrt-cancel-parallel-for#1](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_11.cpp)]

次の例では、[同時実行性::structured_task_group::run_and_wait](reference/structured-task-group-class.md#run_and_wait)メソッドを`parallel_for`使用してアルゴリズムを呼び出します。 `structured_task_group::run_and_wait` メソッドは、指定されたタスクの終了を待機します。 `structured_task_group` オブジェクトによって、処理関数でタスクを取り消すことができるようになります。

[!code-cpp[concrt-task-tree#7](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_12.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
The task group status is: canceled.
```

例外処理を使用して `parallel_for` ループを取り消す例を次に示します。 ランタイムは、例外を呼び出し元のコンテキストにマーシャリングします。

[!code-cpp[concrt-task-tree#9](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_13.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
Caught 50
```

ブール型のフラグを使用して `parallel_for` ループに取り消し処理を組み込む例を次に示します。 この例では、`cancel` メソッドや例外処理を使用して一連のタスク全体を取り消している訳ではないため、すべてのタスクが実行されます。 したがって、この方法では、取り消しメソッドを使用するよりも多くの計算オーバーヘッドが発生する場合があります。

[!code-cpp[concrt-task-tree#8](../../parallel/concrt/codesnippet/cpp/cancellation-in-the-ppl_14.cpp)]

どの取り消し方法にも、他の方法にはない利点があります。 特定のニーズに合った方法を採用してください。

[[トップ](#top)]

## <a name="when-not-to-use-cancellation"></a><a name="when"></a>キャンセルを使用しない場合

取り消し処理は、関連するタスク グループの各メンバーが適時に終了できる場合には適しています。 しかし、取り消し処理がアプリケーションに適さないケースもあります。 たとえば、タスクの取り消しは他の処理と連携して行われるため、個別のタスクがブロックされている場合は、一連のタスク全体を取り消すことができなくなります。 また、あるタスクがまだ開始されていないが、他の実行中のタスクのブロックを解除する場合、タスク グループが取り消されると、そのタスクは開始されません。 これにより、アプリケーションでデッドロックが発生する場合があります。 また、取り消し対象のタスクの子タスクで重要な操作 (リソースの解放など) が実行されるような状況でも、取り消し処理の使用はふさわしくありません。 親タスクを取り消すと一連のタスクがすべて取り消されるため、その操作は実行されなくなります。 この点を示す例については、「並列パターン ライブラリ」の「ベスト プラクティス」の「[取り消しと例外処理がオブジェクト破棄に与える影響について」](../../parallel/concrt/best-practices-in-the-parallel-patterns-library.md#object-destruction)を参照してください。

[[トップ](#top)]

## <a name="related-topics"></a>関連トピック

|Title|説明|
|-----------|-----------------|
|[方法: キャンセル処理を使用して並列ループを中断する](../../parallel/concrt/how-to-use-cancellation-to-break-from-a-parallel-loop.md)|取り消し処理を使用して並列検索アルゴリズムを実装する方法について説明します。|
|[方法: 例外処理を使用して並列ループを中断する](../../parallel/concrt/how-to-use-exception-handling-to-break-from-a-parallel-loop.md)|`task_group` クラスを使用して基本的なツリー構造の検索アルゴリズムを作成する方法を示します。|
|[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)|タスク グループ、軽量タスク、および非同期エージェントによってスローされた例外をランタイムが処理するしくみ、およびアプリケーション内で例外に応答する方法を説明します。|
|[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)|タスクとタスク グループの関係のほか、アプリケーションで非構造化タスクと構造化タスクを使用する方法について説明します。|
|[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)|データのコレクションに対して同時処理を実行する並列アルゴリズムについて説明します。|
|[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)|並列パターン ライブラリの概要を説明します。|

## <a name="reference"></a>リファレンス

[タスク クラス (同時実行ランタイム)](../../parallel/concrt/reference/task-class.md)

[cancellation_token_sourceクラス](../../parallel/concrt/reference/cancellation-token-source-class.md)

[cancellation_tokenクラス](../../parallel/concrt/reference/cancellation-token-class.md)

[task_group クラス](reference/task-group-class.md)

[structured_task_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)

[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)
