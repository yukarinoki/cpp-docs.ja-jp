---
title: スケジュール グループ
ms.date: 11/04/2016
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
ms.openlocfilehash: febcc0a9c7af75801962ea6be687ce87cc5501d4
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295976"
---
# <a name="schedule-groups"></a>スケジュール グループ

このドキュメントでは、同時実行ランタイムのスケジュール グループの役割について説明します。 A*スケジュール グループ*で、またはグループ、関連するタスク化します。 すべてのスケジューラでは、1 つまたは複数のスケジュール グループがあります。 スケジュール グループは、タスク間で高いレベルの局所性が求められる場合 (たとえば、関連するタスクのグループが同一プロセッサ ノードでの実行によって恩恵を受ける場合) に使用します。 逆に、アプリケーションがある特定の品質要件、たとえば、一連のタスクに割り当てられている処理リソースの量を制限する場合に場合は、スケジューラ インスタンスを使用します。 スケジューラ インスタンスの詳細については、次を参照してください。[スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)します。

> [!TIP]
>  コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

すべて`Scheduler`オブジェクトがすべてのスケジューリング ノードの既定のスケジュール グループ。 A*スケジューリング ノード*基になるシステム トポロジにマップされます。 方の値が大きい、プロセッサ パッケージごとに 1 つのスケジュール ノードまたは Non-uniform Memory アーキテクチャ (NUMA) ノードに、ランタイムが作成されます。 スケジュール グループ、タスクを明示的に関連付けないはない場合、スケジューラはタスクを追加するグループを選択します。

`SchedulingProtocol`スケジューラ ポリシー、スケジューラが各スケジュール グループ内のタスクが実行される順序に影響を与えます。 ときに`SchedulingProtocol`に設定されている`EnhanceScheduleGroupLocality`(既定では、)、タスク スケジューラは、現在のタスクが完了するか、協調的に生成するときに使用するスケジュール グループから次のタスクを選択します。 [次へ] の使用可能なグループを移動する前に、タスク スケジューラは作業の現在のスケジュール グループを検索します。 これに対し、`SchedulingProtocol`に設定されている`EnhanceForwardProgress`スケジューラは、各タスクが終了または生成後に次のスケジュール グループに移動します。 これらのポリシーと比較する例を参照してください[方法。スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。

ランタイムを使用して、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)スケジュール グループを表すクラス。 作成する、`ScheduleGroup`オブジェクトを呼び出し、 [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)または[concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)メソッド。 ランタイムでは、参照カウントのメカニズムを使用して、有効期間を制御`ScheduleGroup`オブジェクトの場合と同様`Scheduler`オブジェクト。 作成するときに、`ScheduleGroup`オブジェクト、ランタイムはカウンターを 1 つの参照を設定します。 [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference)メソッドを 1 つの参照カウンターをインクリメントします。 [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release)メソッドをデクリメントを 1 つの参照カウンター。

多くの同時実行ランタイム型では、スケジュール グループと共にオブジェクトを関連付けることができます。 たとえば、 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)などのクラスとメッセージ ブロック クラス[concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)、 [concurrency::join](../../parallel/concrt/reference/join-class.md)、および同時実行::[タイマー](reference/timer-class.md)、取得するコンス トラクターのオーバー ロードされたバージョンの提供、`ScheduleGroup`オブジェクト。 ランタイムを使用して、`Scheduler`これに関連付けられているオブジェクト`ScheduleGroup`タスクをスケジュールするオブジェクト。

使用することも、 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)軽量タスクをスケジュールする方法。 軽量タスクの詳細については、次を参照してください。[軽量タスク](../../parallel/concrt/lightweight-tasks.md)します。

## <a name="example"></a>例

使用がタスクの実行順序を制御するグループをスケジュール例では、次を参照してください。[方法。スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)<br/>
[方法: スケジュール グループを使用して実行順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)
