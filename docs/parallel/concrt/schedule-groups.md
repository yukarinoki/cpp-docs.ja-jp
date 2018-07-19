---
title: スケジュール グループ |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- schedule groups
ms.assetid: 03523572-5891-4d17-89ce-fa795605f28b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c1395fbc58d8a4d1d06cd93eea21c0f3d2dec8c6
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688792"
---
# <a name="schedule-groups"></a>スケジュール グループ
このドキュメントでは、同時実行ランタイムのスケジュール グループの役割について説明します。 A*スケジュール グループ*アフィニティ化、または、関連するタスク グループ化します。 すべてのスケジューラは、1 つまたは複数のスケジュール グループがします。 スケジュール グループは、タスク間で高いレベルの局所性が求められる場合 (たとえば、関連するタスクのグループが同一プロセッサ ノードでの実行によって恩恵を受ける場合) に使用します。 逆に、アプリケーションが特定の品質要件など、一連のタスクに割り当てられている処理リソースの量を制限する場合は、スケジューラ インスタンスを使用します。 スケジューラ インスタンスの詳細については、次を参照してください。[スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)です。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
 各`Scheduler`オブジェクトにスケジュールの各ノードに対して既定のスケジュール グループが存在します。 A*スケジューリング ノード*基になるシステム トポロジをマップします。 方の値が大きい、ランタイムがプロセッサ パッケージごとに 1 つのスケジューリング ノードまたは Non-uniform Memory アーキテクチャ (NUMA) ノードを作成します。 明示的に関連付けないタスクのスケジュール グループに、スケジューラは、タスクを追加するグループを選択します。  
  
 `SchedulingProtocol`スケジューラ ポリシーが、スケジューラが各スケジュール グループ内のタスクが実行される順序に影響します。 ときに`SchedulingProtocol`に設定されている`EnhanceScheduleGroupLocality`(既定値は、)、タスク スケジューラは、それが実行されている現在のタスクが終了または協調的生成時に、スケジュール グループから次のタスクを選択します。 [次へ] の使用可能なグループに移動する前に、タスク スケジューラは作業の現在のスケジュール グループを検索します。 これに対し、`SchedulingProtocol`に設定されている`EnhanceForwardProgress`スケジューラは、各タスクが終了または生成後に次のスケジュール グループに移動します。 これらのポリシーを比較する例は、次を参照してください。[する方法: スケジュール グループの順序の実行に影響を使用する](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)です。  
  

 ランタイムを使用して、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)スケジュール グループを表すクラス。 作成する、`ScheduleGroup`オブジェクトを呼び出し、 [concurrency::CurrentScheduler::CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)または[concurrency::Scheduler::CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)メソッドです。 ランタイム機構を使用して、参照カウントの有効期間を制御する`ScheduleGroup`オブジェクトの場合と同様`Scheduler`オブジェクト。 作成するときに、`ScheduleGroup`オブジェクトのランタイムでは、カウンターを 1 つの参照が設定されます。 [Concurrency::ScheduleGroup::Reference](reference/schedulegroup-class.md#reference)メソッドは、1 つ参照カウンターをインクリメントします。 [Concurrency::ScheduleGroup::Release](reference/schedulegroup-class.md#release)メソッド デクリメント参照カウンターを 1 です。  
  
 同時実行ランタイムでさまざまな種類では、スケジュール グループと共にオブジェクトを関連付けることができます。 たとえば、 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)などのクラスとメッセージ ブロック クラス[concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)、 [concurrency::join](../../parallel/concrt/reference/join-class.md)、および同時実行::[タイマー](reference/timer-class.md)を受け取るコンス トラクターのオーバー ロードされたバージョンの提供、`ScheduleGroup`オブジェクト。 ランタイムを使用して、`Scheduler`これに関連付けられているオブジェクト`ScheduleGroup`タスクをスケジュールするオブジェクト。  
  
 使用することも、 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)軽量タスクをスケジュールする方法です。 軽量タスクの詳細については、次を参照してください。[軽量タスク](../../parallel/concrt/lightweight-tasks.md)です。  

  
## <a name="example"></a>例  
 例については使用がタスクの実行順序を制御するグループをスケジュールする、次を参照してください。[する方法: スケジュール グループの順序の実行に影響を使用する](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)です。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [スケジューラ インスタンス](../../parallel/concrt/scheduler-instances.md)   
 [方法: スケジュール グループを使用して実行順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)

