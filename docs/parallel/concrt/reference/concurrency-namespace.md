---
title: 同時実行 Namespace |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- concurrent_priority_queue/concurrency
- agents/concurrency
- concurrent_vector/concurrency
- concrt/concurrency
- internal_split_ordered_list/concurrency
- concurrent_queue/concurrency
- pplcancellation_token/concurrency
- pplinterface/concurrency
- ppltasks/concurrency
- ppl/concurrency
- concurrent_unordered_map/concurrency
- concrtrm/concurrency
- concurrent_unordered_set/concurrency
- pplconcrt/concurrency
- internal_concurrent_hash/concurrency
dev_langs:
- C++
helpviewer_keywords:
- Concurrency namespace
ms.assetid: f1d33ca2-679b-4442-b140-22a9d9df61d1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 324acb33998246933b0c426357368247c6689c47
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43211318"
---
# <a name="concurrency-namespace"></a>concurrency 名前空間
`Concurrency` 名前空間には、C++ 向けの並列プログラミング フレームワークである同時実行ランタイムにアクセスするためのクラスおよび関数が用意されています。 詳細については、「[同時実行ランタイム](../../../parallel/concrt/concurrency-runtime.md)」を参照してください。  
  
## <a name="syntax"></a>構文  
  
```  
namespace concurrency;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="namespaces"></a>名前空間  
  
|名前|説明|  
|----------|-----------------|  
|[concurrency::extensibility Namespace](https://msdn.microsoft.com/16a86ff2-128e-4edf-89e4-38aac79c81f9)||  
  
### <a name="typedefs"></a>Typedefs  
  
|名前|説明|  
|----------|-----------------|  
|`runtime_object_identity`|各メッセージ インスタンスには、メッセージング コンポーネント間でメッセージ インスタンスの複製または受け渡しを行うときに使用する ID があります。 メッセージ オブジェクトのアドレスをこの ID として指定することはできません。|  
|`task_status`|タスクの終了状態を表す型。 有効値は `completed` または `canceled` です。|  
|`TaskProc`|`void (__cdecl * TaskProc)(void *)` として定義される、タスクの基本抽象化です。 `TaskProc` は、タスクの本体を呼び出すために呼び出されます。|  
|`TaskProc_t`|`void (__cdecl * TaskProc_t)(void *)` として定義される、タスクの基本抽象化です。 `TaskProc` は、タスクの本体を呼び出すために呼び出されます。|  
  
### <a name="classes"></a>クラス  
  
|名前|説明|  
|----------|-----------------|  
|[affinity_partitioner クラス](affinity-partitioner-class.md)|`affinity_partitioner` クラスは `static_partitioner` クラスに似ていますが、ワーカー スレッドへのマッピングのサブ範囲の選択によってキャッシュの関係が向上します。 同じデータ セットに対してループ処理が再実行されるときにパフォーマンスを大幅に向上させることができ、データはキャッシュに収まります。 データの局所性のメリットを利用するには、特定のデータ セットに対して実行される並列ループの以降のイテレーションで、同じ `affinity_partitioner` オブジェクトを使用する必要があります。|  
|[agent クラス](agent-class.md)|すべての独立エージェントの基底クラスとして使用されるクラスです。 他のエージェントに状態が表示されないようにしたり、メッセージ渡しでやり取りしたりする目的で使用されます。|  
|[auto_partitioner クラス](auto-partitioner-class.md)|`auto_partitioner` クラスは、反復処理する範囲を分割するために、既定のメソッド `parallel_for`、`parallel_for_each`、および `parallel_transform` の使用を表します。 このパーティション分割のメソッドでは、負荷分散および反復ごとの取り消しで範囲スティーリングが使用されます。|  
|[bad_target クラス](bad-target-class.md)|このクラスは、実行する操作の無効なターゲットへのポインターがメッセージング ブロックに渡された場合にスローされる例外を表します。|  
|[call クラス](call-class.md)|`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。|  
|[cancellation_token クラス](cancellation-token-class.md)|`cancellation_token` クラスは、ある操作の取り消しが要求されたかどうかを判断する機能を表します。 特定のトークンを `task_group`、`structured_task_group`、または `task` に関連付けると、暗黙的な取り消しを指定できます。 関連付けられた `cancellation_token_source` が取り消されたときに、取り消すためにポーリングしたり、コールバックを登録したりすることもできます。|  
|[cancellation_token_registration クラス](cancellation-token-registration-class.md)|`cancellation_token_registration` クラスは、`cancellation_token` からのコールバック通知を表します。 `register` の `cancellation_token` メソッドを使用して取り消し発生の通知を受け取るとき、`cancellation_token_registration` オブジェクトはハンドルとしてコールバックに返されます。したがって、呼び出し元は `deregister` メソッドを使用して、特定のコールバックが以降行われないように要求できます。|  
|[cancellation_token_source クラス](cancellation-token-source-class.md)|`cancellation_token_source` クラスは、取り消し可能な操作を取り消す機能を表します。|  
|[choice クラス](choice-class.md)|`choice` メッセージング ブロックは、複数のソースと単一のターゲットを持つブロックであり、一連のソースとの制御フローの相互作用を表します。 choice ブロックは、複数のソースのいずれかがメッセージを生成するのを待ち、そのメッセージを生成したソースのインデックスを伝達します。|  
|[combinable クラス](combinable-class.md)|`combinable<T>` オブジェクトは、スレッド プライベートなデータのコピーを提供し、並列アルゴリズムにおいてロック制御不要なスレッド ローカルのサブ計算を実行するために用意されています。 並列操作の最後に、スレッド プライベート サブ計算を最終結果にマージできます。 共有変数に多数の競合が発生する可能性がある場合、共有変数の代わりにこのクラスを使用することにより、パフォーマンスを改善できます。|  
|[concurrent_priority_queue クラス](concurrent-priority-queue-class.md)|`concurrent_priority_queue` クラスは、複数のスレッドが項目を同時にプッシュおよびポップできるようにするコンテナーです。 項目は優先順位の順にポップされます。この優先順位は、テンプレート引数として指定されたファンクタによって決まります。|  
|[concurrent_queue クラス](concurrent-queue-class.md)|`concurrent_queue` クラスは、キューの要素に先入れ先出し方式でアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、`push`、`try_pop` などの特定の同時実行セーフな操作を実行できます。|  
|[concurrent_unordered_map クラス](concurrent-unordered-map-class.md)|`concurrent_unordered_map` クラスは、`std::pair<const K, _Element_type>` 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。 このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。|  
|[concurrent_unordered_multimap クラス](concurrent-unordered-multimap-class.md)|`concurrent_unordered_multimap` クラスは、`std::pair<const K, _Element_type>` 型要素の可変長シーケンスを制御する同時実行セーフなコンテナーです。 このシーケンスは、同時実行セーフな追加、要素アクセス、反復子アクセス、反復子走査の各操作を実行できるように表されます。|  
|[concurrent_unordered_multiset クラス](concurrent-unordered-multiset-class.md)|`concurrent_unordered_multiset`クラスは、同時実行セーフなコンテナー K. 型の要素の可変長シーケンスを制御します。により、同時実行セーフな方法で、シーケンスが表される要素へのアクセス、反復子アクセス、および反復子走査の各操作を追加します。|  
|[concurrent_unordered_set クラス](concurrent-unordered-set-class.md)|`concurrent_unordered_set`クラスは、同時実行セーフなコンテナー K. 型の要素の可変長シーケンスを制御します。により、同時実行セーフな方法で、シーケンスが表される要素へのアクセス、反復子アクセス、および反復子走査の各操作を追加します。|  
|[concurrent_vector クラス](concurrent-vector-class.md)|`concurrent_vector` クラスは、任意の要素にランダムにアクセスできるようにするシーケンス コンテナー クラスです。 これを使用すると、同時実行セーフな追加、要素アクセス、反復子アクセス、および反復子走査の各操作を実行できます。|  
|[Context クラス](context-class.md)|実行コンテキストの抽象化を表します。|  
|[context_self_unblock クラス](context-self-unblock-class.md)|このクラスは、同じコンテキストから `Unblock` オブジェクトの `Context` メソッドが呼び出された場合にスローされる例外を表します。 これは、特定のコンテキストがそれ自体のブロックを解除しようとしたことを示します。|  
|[context_unblock_unbalanced クラス](context-unblock-unbalanced-class.md)|このクラスは、`Block` オブジェクトの `Unblock` メソッドと `Context` メソッドの呼び出しが正しく対になっていない場合にスローされる例外を表します。|  
|[critical_section クラス](critical-section-class.md)|同時実行ランタイムを明示的に認識する再入不可能なミューテックスです。|  
|[CurrentScheduler クラス](currentscheduler-class.md)|呼び出し元コンテキストに関連付けられている現在のスケジューラの抽象化を表します。|  
|[default_scheduler_exists クラス](default-scheduler-exists-class.md)|このクラスは、既定のスケジューラが既にプロセス内に存在するときに `Scheduler::SetDefaultSchedulerPolicy` メソッドが呼び出された場合にスローされる例外を表します。|  
|[event クラス](event-class.md)|同時実行ランタイムを明示的に認識する手動リセット イベントです。|  
|[improper_lock クラス](improper-lock-class.md)|このクラスは、ロックが正しく取得されなかった場合にスローされる例外を表します。|  
|[improper_scheduler_attach クラス](improper-scheduler-attach-class.md)|このクラスは、現在のコンテキストに既にアタッチされている `Attach` オブジェクトで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。|  
|[improper_scheduler_detach クラス](improper-scheduler-detach-class.md)|このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによってスケジューラにアタッチされていないコンテキストで `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。|  
|[improper_scheduler_reference クラス](improper-scheduler-reference-class.md)|このクラスは、終了中の `Reference` オブジェクトで、スケジューラに属していないコンテキストから `Scheduler` メソッドが呼び出された場合にスローされる例外を表します。|  
|[invalid_link_target クラス](invalid-link-target-class.md)|このクラスは、メッセージング ブロックの `link_target` メソッドが呼び出されたときに、そのメッセージング ブロックがターゲットにリンクできない場合にスローされる例外を表します。 この例外の原因としては、メッセージング ブロックのリンク数の上限を超えた場合、または特定のターゲットを同じソースに 2 回リンクしようとした場合があります。|  
|[invalid_multiple_scheduling クラス](invalid-multiple-scheduling-class.md)|このクラスは、`task_handle` オブジェクトまたは `run` オブジェクトの `task_group` メソッドを使用して `structured_task_group` オブジェクトが複数回スケジュールされた場合、間に `wait` メソッドまたは `run_and_wait` メソッドを呼び出さなかったときにスローされる例外を表します。|  
|[invalid_operation クラス](invalid-operation-class.md)|このクラスは、同時実行ランタイムによってスローされる他の例外の種類によって正確に記述されない無効な操作を実行しようとした場合にスローされる例外を表します。|  
|[invalid_oversubscribe_operation クラス](invalid-oversubscribe-operation-class.md)|このクラスは、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `false` メソッドを事前に呼び出さずに、`Context::Oversubscribe` パラメーターが `_BeginOversubscription` に設定された `true` メソッドを呼び出した場合にスローされる例外を表します。|  
|[invalid_scheduler_policy_key クラス](invalid-scheduler-policy-key-class.md)|このクラスは、無効なキーまたは不明なキーが `SchedulerPolicy` オブジェクトのコンストラクターに渡された場合、あるいは、本来他の方法 (`SetPolicyValue` メソッドなど) で変更する必要のあるキーが `SchedulerPolicy` オブジェクトの `SetConcurrencyLimits` メソッドに渡された場合にスローされる例外を表します。|  
|[invalid_scheduler_policy_thread_specification クラス](invalid-scheduler-policy-thread-specification-class.md)|このクラスは、`SchedulerPolicy` オブジェクトの同時実行数の限度を設定する際に、`MinConcurrency` キーに指定された値が `MaxConcurrency` キーの値よりも小さい場合にスローされる例外を表します。|  
|[invalid_scheduler_policy_value クラス](invalid-scheduler-policy-value-class.md)|このクラスは、`SchedulerPolicy` オブジェクトのポリシー キーがそのキーの無効な値に設定された場合にスローされる例外を表します。|  
|[ISource クラス](isource-class.md)|`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。 ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。|  
|[ITarget クラス](itarget-class.md)|`ITarget` クラスは、すべてのターゲット ブロックのインターフェイスです。 ターゲット ブロックは、`ISource` ブロックから提供されたメッセージを処理します。|  
|[join クラス](join-class.md)|`join` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、各ソースから、種類が `T` であるメッセージを結合します。|  
|[location クラス](location-class.md)|ハードウェアの物理位置の抽象化です。|  
|[message クラス](message-class.md)|メッセージング ブロック間で渡されるデータ ペイロードが格納される、基本的なメッセージ エンベロープ。|  
|[message_not_found クラス](message-not-found-class.md)|このクラスは、要求されたメッセージがメッセージング ブロックで見つからない場合にスローされる例外を表します。|  
|[message_processor クラス](message-processor-class.md)|`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。 メッセージの順序は保証されません。|  
|[missing_wait クラス](missing-wait-class.md)|このクラスは、`task_group` オブジェクトまたは `structured_task_group` オブジェクトのデストラクターの実行時に、そのオブジェクトにスケジュールされたタスクがまだ存在する場合にスローされる例外を表します。 例外の結果としてのスタック アンワインドによりデストラクターが実行される場合、この例外はスローされません。|  
|[multi_link_registry クラス](multi-link-registry-class.md)|`multi_link_registry` オブジェクトは、複数のソース ブロックまたは複数のターゲット ブロックを管理する `network_link_registry` です。|  
|[multitype_join クラス](multitype-join-class.md)|`multitype_join` メッセージング ブロックは、複数のソースと単一のターゲットを持つメッセージング ブロックで、それぞれのソースから受け取った異なる種類のメッセージを 1 つに結合して、結合されたメッセージのタプルをターゲットに渡します。|  
|[nested_scheduler_missing_detach クラス](nested-scheduler-missing-detach-class.md)|このクラスは、`CurrentScheduler::Detach` オブジェクトの `Attach` メソッドによって別のスケジューラにアタッチされているコンテキストで `Scheduler` メソッドが呼び出されなかったことを、同時実行ランタイムが検出した場合にスローされる例外を表します。|  
|[network_link_registry クラス](network-link-registry-class.md)|`network_link_registry` 抽象基底クラスによって、ソース ブロックとターゲット ブロック間のリンクを管理します。|  
|[operation_timed_out クラス](operation-timed-out-class.md)|このクラスは、操作がタイムアウトした場合にスローされる例外を表します。|  
|[ordered_message_processor クラス](ordered-message-processor-class.md)|`ordered_message_processor` は、メッセージ ブロックがメッセージを受け取った順序で処理できるようにする `message_processor` です。|  
|[overwrite_buffer クラス](overwrite-buffer-class.md)|`overwrite_buffer` メッセージング ブロックは、一度に 1 つのメッセージを格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。 新しいメッセージが与えられると、それまで格納されていたメッセージは上書きされます。|  
|[progress_reporter クラス](progress-reporter-class.md)|progress reporter クラスは、特定の型の進行状況の通知をレポートできます。 各 progress_reporter オブジェクトが、特定の非同期アクションまたは操作にバインドされます。|  
|[propagator_block クラス](propagator-block-class.md)|`propagator_block` クラスは、ソースでもありターゲットでもあるメッセージ ブロックの抽象基底クラスです。 `source_block` クラスと `target_block` クラスの両方の機能が組み合わされています。|  
|[reader_writer_lock クラス](reader-writer-lock-class.md)|ローカルのみのスピンを行う、ライター優先キュー ベースのリーダー ライター ロックです。 ロックはライターに先入れ先出し (FIFO: First In First Out) アクセスを許可し、ライターに連続的な負荷がかかる状況ではリーダーが処理を実行できなくします。|  
|[ScheduleGroup クラス](schedulegroup-class.md)|スケジュール グループの抽象化を表します。 スケジュール グループは、(別のグループに移動する前に同じグループ内の別のタスクを実行することで) 一時的に、または (同じ NUMA ノードまたは物理ソケットの同じグループ内の複数の項目を実行することにより) 空間的に、短い間隔でスケジュールするとメリットがある関連作業のセットを編成します。|  
|[Scheduler クラス](scheduler-class.md)|同時実行ランタイム スケジューラの抽象化を表します。|  
|[scheduler_not_attached クラス](scheduler-not-attached-class.md)|このクラスは、現在のコンテキストにスケジューラがアタッチされている必要がある操作を実行するときにスケジューラがアタッチされていない場合にスローされる例外を表します。|  
|[scheduler_resource_allocation_error クラス](scheduler-resource-allocation-error-class.md)|このクラスは、同時実行ランタイムでクリティカル リソースを取得できないためにスローされる例外を表します。|  
|[scheduler_worker_creation_error クラス](scheduler-worker-creation-error-class.md)|このクラスは、同時実行ランタイムでワーカー実行コンテキストを作成できないためにスローされる例外を表します。|  
|[SchedulerPolicy クラス](schedulerpolicy-class.md)|`SchedulerPolicy` クラスには、ポリシー要素ごとに 1 つずつ、スケジューラ インスタンスの動作を制御するキーと値のペアのセットが含まれています。|  
|[simple_partitioner クラス](simple-partitioner-class.md)|`simple_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。各チャンクには、少なくともチャンク サイズによって指定された数のイテレーションが含まれます。|  
|[single_assignment クラス](single-assignment-class.md)|`single_assignment` メッセージング ブロックは、一度だけ書き込むことができる `propagator_block` を 1 つ格納できる、複数のターゲットと複数のソースを持つ順序付けられた `message` です。|  
|[single_link_registry クラス](single-link-registry-class.md)|`single_link_registry` オブジェクトは、単一のソース ブロックまたはターゲット ブロックのみを管理する `network_link_registry` です。|  
|[source_block クラス](source-block-class.md)|`source_block` クラスは、ソースのみのブロックの抽象基底クラスです。 このクラスには、基本的なリンク管理機能および一般的なエラー チェック機能が用意されています。|  
|[source_link_manager クラス](source-link-manager-class.md)|`source_link_manager` オブジェクトは、`ISource` ブロックへのメッセージング ブロック ネットワーク リンクを管理します。|  
|[static_partitioner クラス](static-partitioner-class.md)|`static_partitioner` クラスは、`parallel_for` によって反復処理される範囲の静的パーティション分割を表します。 パーティショナーは範囲をチャンクに分割します。チャンクの数は、基になるスケジューラが使用できるワーカーと同じ数にします。|  
|[structured_task_group クラス](structured-task-group-class.md)|`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。 `structured_task_group` オブジェクトを使用して個々の並列タスクを `task_handle` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。|  
|[target_block クラス](target-block-class.md)|`target_block` クラスは、基本的なリンク管理機能と、ターゲットのみのブロックのエラー チェック機能を実現する抽象基底クラスです。|  
|[task クラス (同時実行ランタイム)](task-class.md)|並列パターン ライブラリ (PPL) `task` クラス。 `task` オブジェクトは、非同期的に、他のタスクと同時に実行できる処理、および同時実行ランタイムの並列アルゴリズムによって生成される並列処理を表します。 正常に終了した場合は、型 `_ResultType` の結果が生成されます。 型 `task<void>` のタスクでは結果が作成されません。 タスクは、他のタスクと関係なく待機および取り消しできます。 また、continuations(`then`)、および join(`when_all`) パターンと choice(`when_any`) パターンを使用して、他のタスクと共に構成することもできます。|  
|[task_canceled クラス](task-canceled-class.md)|このクラスは、現在のタスクを強制的に取り消すために PPL タスク レイヤーによってスローされる例外を表します。 によってもスローされます、`get()`メソッド[タスク](https://msdn.microsoft.com/5389e8a5-5038-40b6-844a-55e9b58ad35f)、取り消されたタスク。|  
|[task_completion_event クラス](task-completion-event-class.md)|`task_completion_event` クラスを使用すると、条件が満たされるまで、または外部イベントに応答してタスクを開始するまで、タスクの実行を遅延できます。|  
|[task_continuation_context クラス](task-continuation-context-class.md)|`task_continuation_context` クラスを使用すると、継続する場所を指定できます。 のみ、UWP アプリからこのクラスを使用すると便利です。 非 Windows ランタイム アプリでは、タスクの継続の実行コンテキストは、ランタイムによって決定され、構成できません。|  
|[task_group クラス](task-group-class.md)|`task_group` クラスは、待機または取り消しができる並列処理のコレクションを表します。|  
|[task_handle クラス](task-handle-class.md)|`task_handle` クラスは個々の並列作業項目を表します。 このクラスは、1 つの処理を実行するために必要な命令およびデータをカプセル化します。|  
|[task_options クラス (同時実行ランタイム)](task-options-class-concurrency-runtime.md)|タスクの作成に使用できるオプションを表します。|  
|[timer クラス](timer-class.md)|`timer` メッセージング ブロックは単一のターゲットを持つ `source_block` であり、指定された時間の経過後か、特定の間隔で、メッセージをターゲットに送信することができます。|  
|[transformer クラス](transformer-class.md)|`transformer` メッセージング ブロックは、単一のターゲットと複数のソースを持つ順序付けられた `propagator_block` であり、1 つの種類のメッセージを複数受け入れ、別の種類のメッセージを無制限に格納することができます。|  
|[unbounded_buffer クラス](unbounded-buffer-class.md)|`unbounded_buffer` メッセージング ブロックは、メッセージを無制限に格納することができる、複数のターゲットと複数のソースを持つ順序付けられた `propagator_block` です。|  
|[unsupported_os クラス](unsupported-os-class.md)|このクラスは、サポート外のオペレーティング システムが使用された場合にスローされる例外を表します。|  
  
### <a name="structures"></a>構造体  
  
|名前|説明|  
|----------|-----------------|  
|[DispatchState 構造体](dispatchstate-structure.md)|`DispatchState` 構造体は、状態を `IExecutionContext::Dispatch` メソッドに転送するために使用されます。 `Dispatch` メソッドが `IExecutionContext` インターフェイスで呼び出される状況を示します。|  
|[IExecutionContext 構造体](iexecutioncontext-structure.md)|特定の仮想プロセッサで実行でき、協調的にコンテキストを切り替えることができる実行コンテキストへのインターフェイスです。|  
|[IExecutionResource 構造体](iexecutionresource-structure.md)|ハードウェア スレッドの抽象化です。|  
|[IResourceManager 構造体](iresourcemanager-structure.md)|同時実行ランタイムのリソース マネージャーに対するインターフェイスです。 これは、スケジューラがリソース マネージャーと通信する際に使用されるインターフェイスです。|  
|[IScheduler 構造体](ischeduler-structure.md)|作業スケジューラの抽象化のインターフェイスです。 同時実行ランタイムのリソース マネージャーは、このインターフェイスを使用して作業スケジューラと通信します。|  
|[ISchedulerProxy 構造体](ischedulerproxy-structure.md)|スケジューラは、このインターフェイスを使用して同時実行ランタイムのリソース マネージャーと通信して、リソース割り当てをネゴシエートします。|  
|[IThreadProxy 構造体](ithreadproxy-structure.md)|実行スレッドの抽象化です。 作成するスケジューラの `SchedulerType` ポリシー キーに応じて、リソース マネージャーは、通常の Win32 スレッドまたはユーザー モード スケジュール可能 (UMS: User-Mode Schedulable) スレッドによってサポートされるスレッド プロキシを許可します。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでサポートされます。|  
|[ITopologyExecutionResource 構造体](itopologyexecutionresource-structure.md)|リソース マネージャーで定義される実行リソースへのインターフェイスです。|  
|[ITopologyNode 構造体](itopologynode-structure.md)|リソース マネージャーで定義されるトポロジ ノードへのインターフェイスです。 ノードには 1 つ以上の実行リソースが含まれます。|  
|[IUMSCompletionList 構造体](iumscompletionlist-structure.md)|UMS の完了リストを表します。 UMS スレッドがブロックされると、基になる仮想プロセッサ ルートでスケジュールする内容を決定するためにスケジューラで指定されているスケジュールのコンテキストがディスパッチされ、元のスレッドがブロックされます。 元のスレッドがブロックされない場合、オペレーション システムは、このインターフェイスからアクセスできる完了リストのキューにそれを配置します。 スケジューラは指定されたスケジュール コンテキスト、または作業を検索するその他の場所にある完了リストを照会できます。|  
|[IUMSScheduler 構造体](iumsscheduler-structure.md)|同時実行ランタイムのリソース マネージャーによってユーザー モード スケジュール可能 (UMS) スレッドが渡される必要がある作業スケジューラの抽象化のインターフェイスです。 リソース マネージャーでは、このインターフェイスを使用して UMS スレッド スケジューラと通信します。 `IUMSScheduler` インターフェイスは `IScheduler` のインターフェイスから継承されます。|  
|[IUMSThreadProxy 構造体](iumsthreadproxy-structure.md)|実行スレッドの抽象化です。 ユーザー モード スケジュール可能 (UMS) スレッドをスケジューラに付与するには、スケジューラ ポリシー要素 `SchedulerKind` の値を `UmsThreadDefault` に設定し、さらに `IUMSScheduler` インターフェイスを実装する必要があります。 UMS スレッドは、Windows 7 以上のバージョンの 64 ビット オペレーティング システムでのみサポートされます。|  
|[IUMSUnblockNotification 構造体](iumsunblocknotification-structure.md)|ブロックされ、スケジューラの指定されたスケジュール コンテキストに制御を戻すことをトリガーされたスレッド プロキシが、ブロック解除され、スケジュールできる状態であることを示す、リソース マネージャーからの通知を表します。 このインターフェイスは、`GetContext` メソッドから返される、スレッド プロキシの関連付けられた実行コンテキストが再スケジュールされると無効になります。|  
|[IVirtualProcessorRoot 構造体](ivirtualprocessorroot-structure.md)|スレッド プロキシが実行できるハードウェア スレッドの抽象化です。|  
|[scheduler_interface 構造体](scheduler-interface-structure.md)|スケジューラ インターフェイス|  
|[scheduler_ptr 構造体 (同時実行ランタイム)](scheduler-ptr-structure-concurrency-runtime.md)|スケジューラへのポインターを表します。 このクラスは、生のポインターを使用して、shared_ptr またはプレーンな参照だけを使用して共有有効期間の指定を許可する存在します。|  
  
### <a name="enumerations"></a>列挙  
  
|name|説明|  
|----------|-----------------|  
|[agent_status](concurrency-namespace-enums.md#agent_status)|`agent` の有効な状態。|  
|[Agents_EventType](concurrency-namespace-enums.md#agents_eventtype)|エージェント ライブラリによって提供されるトレース機能を使用してトレースできるイベントの種類。|  
|[ConcRT_EventType](concurrency-namespace-enums.md#concrt_eventtype)|同時実行ランタイムによって提供されるトレース機能を使用してトレースできるイベントの種類。|  
|[Concrt_TraceFlags](concurrency-namespace-enums.md#concrt_traceflags)|イベントの種類のトレース フラグ。|  
|[CriticalRegionType](concurrency-namespace-enums.md#criticalregiontype)|コンテキストが存在するクリティカル領域の種類。|  
|[DynamicProgressFeedbackType](concurrency-namespace-enums.md#dynamicprogressfeedbacktype)|`DynamicProgressFeedback` ポリシーによって使用され、スケジューラのリソースのバランスを再調整する際の判断基準として、スケジューラから収集された統計情報に従うか、または `Activate` インターフェイスの `Deactivate` メソッドおよび `IVirtualProcessorRoot` メソッドの呼び出しによってアイドル状態との間で状態が変化する仮想プロセッサのみに基づくかを示します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)します。|  
|[join_type](concurrency-namespace-enums.md#join_type)|`join` メッセージング ブロックの種類。|  
|[message_status](concurrency-namespace-enums.md#message_status)|ブロックへの `message` オブジェクトの提供に対する有効な応答。|  
|[PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)|ポリシー キーは、スケジューラの動作をさまざまな側面から表します。 各ポリシー要素は、キーと値の組み合わせで表現されます。 スケジューラのスケジューラ ポリシーとその影響に関する詳細については、次を参照してください。[タスク スケジューラ](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。|  
|[SchedulerType](concurrency-namespace-enums.md#schedulertype)|基になる実行コンテキスト用にスケジューラが利用するスレッドの種類を示すために、`SchedulerKind` ポリシーにより使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)します。|  
|[SchedulingProtocolType](concurrency-namespace-enums.md#schedulingprotocoltype)|スケジューラに使用されるスケジューリング アルゴリズムを記述するために、`SchedulingProtocol` ポリシーによって使用されます。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)します。|  
|[SwitchingProxyState](concurrency-namespace-enums.md#switchingproxystate)|あるスレッド プロキシから別のスレッド プロキシへの協調的なコンテキスト切り替えを実行するときに、スレッド プロキシの状態を示すために使用します。|  
|[task_group_status](concurrency-namespace-enums.md#task_group_status)|`task_group` オブジェクトまたは `structured_task_group` オブジェクトの実行状態を示します。 この型の値は、タスク グループに対してスケジュールされたタスクが完了するのを待機している多数のメソッドによって返されます。|  
|[WinRTInitializationType](concurrency-namespace-enums.md#winrtinitializationtype)|`WinRTInitialization` ポリシーによって使用され、Windows 8 以上のオペレーティング システムで実行されるアプリケーション用のスケジューラ スレッドで、Windows ランタイムを初期化するかどうか、またどのように初期化するかを表します。 使用できるスケジューラ ポリシーの詳細については、次を参照してください。 [PolicyElementKey](concurrency-namespace-enums.md#policyelementkey)します。|  
  
### <a name="functions"></a>関数  
  
|名前|説明|  
|----------|-----------------|  
|[Alloc 関数](concurrency-namespace-functions.md#alloc)|同時実行ランタイムのキャッシュ サブアロケータから、指定したサイズのメモリ ブロックを割り当てます。|  
|[asend 関数](concurrency-namespace-functions.md#asend)|オーバーロードされます。 ターゲット ブロックにデータを反映するタスクをスケジュールする非同期送信操作です。|  
|[cancel_current_task 関数](concurrency-namespace-functions.md#cancel_current_task)|現在実行中のタスクを取り消します。 この関数は、タスクの実行を中止して `canceled` 状態に遷移させるために、タスクの本体から呼び出すことができます。<br /><br /> `task` の本体以外では、この関数を呼び出すシナリオはサポートされません。 これを行うと、アプリケーションのクラッシュや停止など、定義されていない動作が発生します。|  
|[create_async 関数](concurrency-namespace-functions.md#create_async)|ユーザーが指定したラムダまたは関数オブジェクトに基づいて Windows ランタイムの非同期構造を作成します。 `create_async` の戻り値の型は、`IAsyncAction^`、`IAsyncActionWithProgress<TProgress>^`、`IAsyncOperation<TResult>^`、`IAsyncOperationWithProgress<TResult, TProgress>^` のいずれかで、メソッドに渡されるラムダのシグネチャに基づいています。|  
|[create_task 関数](concurrency-namespace-functions.md#create_task)|オーバーロードされます。 作成、PPL[タスク](https://msdn.microsoft.com/5389e8a5-5038-40b6-844a-55e9b58ad35f)オブジェクト。 `create_task` は、タスク コンストラクターを使用した任意の場所で使用できます。 タスクの作成中に `auto` キーワードが使用できるようになるため、これは参考用として用意されています。|  
|[CreateResourceManager 関数](concurrency-namespace-functions.md#createresourcemanager)|同時実行ランタイムのリソース マネージャーのシングルトン インスタンスを表すインターフェイスを返します。 リソース マネージャーは、相互の連携を必要とするスケジューラにリソースを割り当てます。|  
|[DisableTracing 関数](concurrency-namespace-functions.md#disabletracing)|同時実行ランタイムでのトレースを無効にします。 この関数は、ETW トレースが既定で未登録であるため非推奨とされます。|  
|[EnableTracing 関数](concurrency-namespace-functions.md#enabletracing)|同時実行ランタイムでトレースを有効にします。 この関数は、ETW トレースが既定でオンであるため非推奨とされます。|  
|[Free 関数](concurrency-namespace-functions.md#free)|以前に `Alloc` メソッドによって同時実行ランタイムのキャッシュ サブアロケータに割り当てられたメモリ ブロックを解放します。|  
|[get_ambient_scheduler 関数 (同時実行ランタイム)](concurrency-namespace-functions.md#get_ambient_scheduler)||  
|[GetExecutionContextId 関数](concurrency-namespace-functions.md#getexecutioncontextid)|`IExecutionContext` インターフェイスを実装する実行コンテキストに割り当てることのできる一意識別子を返します。|  
|[GetOSVersion 関数](concurrency-namespace-functions.md#getosversion)|オペレーティング システムのバージョンを返します。|  
|[GetProcessorCount 関数](concurrency-namespace-functions.md#getprocessorcount)|基になるシステム上のハードウェア スレッドの数を返します。|  
|[GetProcessorNodeCount 関数](concurrency-namespace-functions.md#getprocessornodecount)|基になるシステム上の NUMA ノードまたはプロセッサ パッケージの数を返します。|  
|[GetSchedulerId 関数](concurrency-namespace-functions.md#getschedulerid)|`IScheduler` インターフェイスを実装するスケジューラに割り当てることができる一意識別子を返します。|  
|[interruption_point 関数](concurrency-namespace-functions.md#interruption_point)|取り消しの割り込みポイントを作成します。 この関数が呼び出されるコンテキストで取り消しが進行中の場合、現在実行中の並列処理を中止する内部例外がスローされます。 取り消しが進行中でない場合は、何も実行されません。|  
|[is_current_task_group_canceling 関数](concurrency-namespace-functions.md#is_current_task_group_canceling)|現在のコンテキストで現在インラインで実行されているタスク グループがアクティブなキャンセル処理中である (または間もなくキャンセル処理が開始される) かどうかを示す値を返します。 現在のコンテキストで現在インラインで実行されているタスク グループが存在しない場合は、`false` が返されます。|  
|[make_choice 関数](concurrency-namespace-functions.md#make_choice)|オーバーロードされます。 オプションの `choice` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。|  
|[make_greedy_join 関数](concurrency-namespace-functions.md#make_greedy_join)|オーバーロードされます。 オプションの `greedy multitype_join` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。|  
|[make_join 関数](concurrency-namespace-functions.md#make_join)|オーバーロードされます。 オプションの `non_greedy multitype_join` や `Scheduler`、および 2 つ以上の入力ソースから `ScheduleGroup` メッセージング ブロックを構築します。|  
|[make_task 関数](concurrency-namespace-functions.md#make_task)|`task_handle` オブジェクトを作成するためのファクトリ メソッドです。|  
|[parallel_buffered_sort 関数](concurrency-namespace-functions.md#parallel_buffered_sort)|オーバーロードされます。 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。ただし、`O(n)` 追加スペースが必要で、並べ替えている要素を既定で初期化する必要があります。|  
|[parallel_for 関数](concurrency-namespace-functions.md#parallel_for)|オーバーロードされます。 `parallel_for` は、一定の範囲のインデックスを反復処理し、各反復処理で、ユーザーが指定した関数を並列で実行します。|  
|[parallel_for_each 関数](concurrency-namespace-functions.md#parallel_for_each)|オーバーロードされます。 `parallel_for_each` は、指定された関数を範囲内の各要素に並列で適用します。 意味的には `for_each` 名前空間の `std` 関数と同等ですが、要素に対する反復処理が並列で行われる点、および反復処理の順序が指定されていない点が異なります。 引数 `_Func` は、`operator()(T)` の形式の関数呼び出し演算子をサポートしている必要があります (`T` パラメーターは反復処理するコンテナーの項目の種類を示します)。|  
|[parallel_invoke 関数](concurrency-namespace-functions.md#parallel_invoke)|オーバーロードされます。 パラメーターとして渡された関数オブジェクトを並列実行し、実行が完了するまでブロックします。 各関数オブジェクトは、ラムダ式、関数へのポインター、またはシグネチャ `void operator()()` を持つ関数呼び出し演算子をサポートするオブジェクトになります。|  
|[parallel_radixsort 関数](concurrency-namespace-functions.md#parallel_radixsort)|オーバーロードされます。 基数並べ替えアルゴリズムを使用して、指定された範囲の要素を降順以外の順序で配置します。 これは安定した並べ替え関数で、符号なし整数 (キーなど) に分類されるように要素を投影する投射関数を必要とします。 並べ替えられる要素には既定の初期化が必要です。|  
|[parallel_reduce 関数](concurrency-namespace-functions.md#parallel_reduce)|オーバーロードされます。 連続する部分的な合計を計算することで、指定された範囲のすべての要素の合計を計算します。または、指定された二項演算を使用して取得した、合計以外の連続する部分的な結果を並列で計算します。 `parallel_reduce` は `std::accumulate` と意味が同じです。ただし、結合のための二項演算と、初期値ではなく ID 値が必要です。|  
|[parallel_sort 関数](concurrency-namespace-functions.md#parallel_sort)|オーバーロードされます。 指定された範囲の要素を、降順以外の順序、または二項述語で指定された順序の基準に従って、並列に配置します。 この関数は、比較ベースで不安定なインプレース並べ替えという点で `std::sort` と意味が同じです。|  
|[parallel_transform 関数](concurrency-namespace-functions.md#parallel_transform)|オーバーロードされます。 指定された関数オブジェクトをソース範囲内の各要素、または 2 つのソース範囲内の要素のペアに適用し、関数オブジェクトの戻り値をコピー先の範囲に並列でコピーします。 この関数は、意味的には `std::transform` と同じです。|  
|[receive 関数](concurrency-namespace-functions.md#receive)|オーバーロードされます。 receive の一般的な実装です。これにより、コンテキストで 1 つのソースからのデータを待機し、受け取った値をフィルター処理できます。|  
|[run_with_cancellation_token 関数](concurrency-namespace-functions.md#run_with_cancellation_token)|関数オブジェクトを、指定されたキャンセル トークンのコンテキストですばやく同期的に実行します。|  
|[send 関数](concurrency-namespace-functions.md#send)|オーバーロードされます。 ターゲットがメッセージを受け入れるか拒否するまで待機する同期送信操作です。|  
|[set_ambient_scheduler 関数 (同時実行ランタイム)](concurrency-namespace-functions.md#set_ambient_scheduler)||  
|[set_task_execution_resources 関数](concurrency-namespace-functions.md#set_task_execution_resources)|オーバーロードされます。 同時実行ランタイムの内部ワーカー スレッドが使用する実行リソースを、指定された関係セットに制限します。<br /><br /> このメソッドの呼び出しは、リソース マネージャーの作成前、または 2 つのリソース マネージャーの有効期間の間のみ有効です。 これは、呼び出し時にリソース マネージャーが存在しない限り複数回呼び出すことができます。 関係の制限が設定されたら、次の有効な `set_task_execution_resources` メソッド呼び出しまで保持されます。<br /><br /> 指定された関係マスクは、プロセス関係マスクのサブセットである必要はありません。 プロセス関係は必要に応じて更新されます。|  
|[swap 関数](concurrency-namespace-functions.md#swap)|2 つの `concurrent_vector` オブジェクトの要素を交換します。|  
|[task_from_exception 関数 (同時実行ランタイム)](concurrency-namespace-functions.md#task_from_exception)||  
|[task_from_result 関数 (同時実行ランタイム)](concurrency-namespace-functions.md#task_from_result)||  
|[Trace_agents_register_name 関数](concurrency-namespace-functions.md#trace_agents_register_name)|指定された名前を、ETW トレースのメッセージ ブロックまたはエージェントに関連付けます。|  
|[try_receive 関数](concurrency-namespace-functions.md#try_receive)|オーバーロードされます。 try-receive の一般的な実装です。これにより、コンテキストで 1 つのソースに対してのみデータの検索を実行し、受け取った値をフィルター処理できます。 データが準備されていない場合、メソッドは false を返します。|  
|[wait 関数](concurrency-namespace-functions.md#wait)|指定した時間だけ現在のコンテキストを停止します。|  
|[when_all 関数](concurrency-namespace-functions.md#when_all)|引数として指定されたすべてのタスクが正常に完了したときに正常に完了するタスクを作成します。|  
|[when_any 関数](concurrency-namespace-functions.md#when_any)|オーバーロードされます。 引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。|  
  
### <a name="operators"></a>演算子  
  
|名前|説明|  
|----------|-----------------| 
|[operator!=](concurrency-namespace-operators.md#operator_neq)|演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しくないかどうかを調べます。|  
|[operator&&](concurrency-namespace-operators.md#operator_amp_amp)|オーバーロードされます。 引数として指定された両方のタスクが正常に完了したときに正常に完了するタスクを作成します。|  
|[operator&#124;&#124;](concurrency-namespace-operators.md#operator_lor)|オーバーロードされます。 引数として指定されたいずれかのタスクが正常に完了したときに正常に完了するタスクを作成します。|  
|[operator<](concurrency-namespace-operators.md#operator_lt)|演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより小さいかどうかを調べます。|  
|[operator<=](concurrency-namespace-operators.md#operator_lt_eq)|演算子の左側の `concurrent_vector` オブジェクトが右側の  `concurrent_vector` オブジェクト以下かどうかを調べます。|  
|[operator==](concurrency-namespace-operators.md#operator_eq_eq)|演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトと等しいかどうかを調べます。|  
|[operator>](concurrency-namespace-operators.md#operator_gt)|演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクトより大きいかどうかを調べます。|  
|[operator>=](concurrency-namespace-operators.md#operator_lt_eq)|演算子の左側の `concurrent_vector` オブジェクトが右側の `concurrent_vector` オブジェクト以上であるかどうかを調べます。|  
  
### <a name="constants"></a>定数  
  
|名前|説明|  
|----------|-----------------|  
|[AgentEventGuid](concurrency-namespace-constants1.md#agenteventguid)|同時実行ランタイムのエージェント ライブラリによって生成される ETW イベントを表すカテゴリの GUID ({B9B5B78C-0713-4898-A21A-C67949DCED07})。|  
|[ChoreEventGuid](concurrency-namespace-constants1.md#choreeventguid)|同時実行ランタイムによって生成される ETW イベントのうち、作業またはタスクに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[ConcRT_ProviderGuid](concurrency-namespace-constants1.md#concrt_providerguid)|同時実行ランタイムの ETW プロバイダーの GUID。|  
|[CONCRT_RM_VERSION_1](concurrency-namespace-constants1.md#concrt_rm_version_1)|Visual Studio 2010 で定義されているリソース マネージャー インターフェイスのサポートを示します。|  
|[ConcRTEventGuid](concurrency-namespace-constants1.md#concrteventguid)|同時実行ランタイムによって生成される ETW イベントのうち、別のカテゴリで具体的に説明されていない ETW イベントを表すカテゴリの GUID。|  
|[ContextEventGuid](concurrency-namespace-constants1.md#contexteventguid)|同時実行ランタイムによって生成される ETW イベントのうち、コンテキストに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[COOPERATIVE_TIMEOUT_INFINITE](concurrency-namespace-constants1.md#cooperative_timeout_infinite)|待機がタイムアウトしないことを示す値。|  
|[COOPERATIVE_WAIT_TIMEOUT](concurrency-namespace-constants1.md#cooperative_wait_timeout)|待機がタイムアウトしたことを示す値。|  
|[INHERIT_THREAD_PRIORITY](concurrency-namespace-constants1.md#inherit_thread_priority)|スケジューラのすべてのコンテキストのスレッド優先順位が、スケジューラを作成したスレッドの優先順位と同じになることを示す `ContextPriority` ポリシー キーの特別な値。|  
|[LockEventGuid](concurrency-namespace-constants1.md#lockeventguid)|同時実行ランタイムによって生成される ETW イベントのうち、ロックに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[MaxExecutionResources](concurrency-namespace-constants1.md#maxexecutionresources)|`MinConcurrency` ポリシー キーおよび `MaxConcurrency` ポリシー キーの特殊な値。 他の制約が存在しない場合、既定でコンピューター上のハードウェア スレッドの数になります。|  
|[PPLParallelForeachEventGuid](concurrency-namespace-constants1.md#pplparallelforeacheventguid)|同時実行ランタイムによって生成される ETW イベントのうち、`parallel_for_each` 関数の使用に直接関係する ETW イベントを表すカテゴリの GUID。|  
|[PPLParallelForEventGuid](concurrency-namespace-constants1.md#pplparallelforeventguid)|同時実行ランタイムによって生成される ETW イベントのうち、`parallel_for` 関数の使用に直接関係する ETW イベントを表すカテゴリの GUID。|  
|[PPLParallelInvokeEventGuid](concurrency-namespace-constants1.md#pplparallelinvokeeventguid)|同時実行ランタイムによって生成される ETW イベントのうち、`parallel_invoke` 関数の使用に直接関係する ETW イベントを表すカテゴリの GUID。|  
|[ResourceManagerEventGuid](concurrency-namespace-constants1.md#resourcemanagereventguid)|同時実行ランタイムによって生成される ETW イベントのうち、リソース マネージャーに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[ScheduleGroupEventGuid](concurrency-namespace-constants1.md#schedulegroupeventguid)|同時実行ランタイムによって生成される ETW イベントのうち、スケジュール グループに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[SchedulerEventGuid](concurrency-namespace-constants1.md#schedulereventguid)|同時実行ランタイムによって生成される ETW イベントのうち、スケジューラ アクティビティに直接関係する ETW イベントを表すカテゴリの GUID。|  
|[VirtualProcessorEventGuid](concurrency-namespace-constants1.md#virtualprocessoreventguid)|同時実行ランタイムによって生成される ETW イベントのうち、仮想プロセッサに直接関係する ETW イベントを表すカテゴリの GUID。|  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h、concrt.h、concrtrm.h、concurrent_priority_queue.h、concurrent_queue.h、concurrent_unordered_map.h、concurrent_unordered_set.h、concurrent_vector.h、internal_concurrent_hash.h、internal_split_ordered_list.h、ppl.h、pplcancellation_token.h、pplconcrt.h、pplinterface.h、ppltasks.h  
  
## <a name="see-also"></a>関連項目  
 [参照](reference-concurrency-runtime.md)

