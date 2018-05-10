---
title: スケジューラ インスタンス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f09a5708fd9140619eea60fb8e483c2e26165d1
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="scheduler-instances"></a>スケジューラ インスタンス
このドキュメントで使用する方法と、同時実行ランタイム スケジューラ インスタンスの役割の説明、 [concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)と[concurrency::currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md)クラスを作成および管理するにはスケジューラ インスタンス。 スケジューラ インスタンスは、特定の種類のワークロードに明示的なスケジューリング ポリシーを関連付ける場合に便利です。 たとえば、昇格したスレッド優先順位で一部のタスクを実行するようにスケジューラ インスタンスを 1 つ作成し、他のタスクについては既定のスケジューラを使用して通常のスレッド優先順位で実行することができます。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
##  <a name="top"></a> セクション  
  
-   [スケジューラと CurrentScheduler クラス](#classes)  
  
-   [スケジューラ インスタンスを作成します。](#creating)  
  
-   [スケジューラ インスタンスの有効期間を管理します。](#managing)  
  
-   [メソッドと機能](#features)  
  
-   [例](#example)  
  
##  <a name="classes"></a> スケジューラと CurrentScheduler クラス  
 タスク スケジューラにより、1 つまたは複数を使用するアプリケーション*スケジューラ インスタンス*作業をスケジュールします。 [Concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)クラスが、スケジューラ インスタンスを表し、タスクのスケジュール設定に関連する機能をカプセル化します。  
  
 スケジューラにアタッチされているスレッドと呼ばれる、*実行コンテキスト*、または単*コンテキスト*です。 1 つのスケジューラは、いつでも、現在のコンテキストでアクティブにできます。 アクティブなスケジューラとも呼ばれます、*現在のスケジューラ*です。 同時実行ランタイムを使用して、 [concurrency::currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md)アクセスを現在のスケジューラに提供するクラス。 1 つのコンテキストの現在のスケジューラは、別のコンテキストの現在のスケジューラと異なることができます。 ランタイムは、現在のスケジューラのプロセス レベルの表現を提供しません。  
  
 通常、`CurrentScheduler`クラスは、現在のスケジューラへのアクセスに使用します。 `Scheduler`クラスは、現在のものではないスケジューラを管理する必要がある場合に便利です。  
  
 次のセクションでは、作成してスケジューラ インスタンスを管理する方法について説明します。 これらのタスクを示す完全な例を次を参照してください。[する方法: スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="creating"></a> スケジューラ インスタンスを作成します。  
 これら 3 つの方法を作成する、`Scheduler`オブジェクト。  
  
-   スケジューラが存在しない場合、ランタイムは、共通言語ランタイムの機能、たとえば、並列アルゴリズムを使用して作業を実行するときに、既定のスケジューラを作成します。 既定のスケジューラでは、並列処理を開始するコンテキストの現在のスケジューラになります。  
  

-   [Concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create)メソッドを作成、`Scheduler`オブジェクトを特定のポリシーを使用し、そのスケジューラを現在のコンテキストに関連付けます。  
  
-   [:Create](reference/scheduler-class.md#create)メソッドを作成、`Scheduler`オブジェクトが特定のポリシーを使用しますが、関連付けられませんが、現在のコンテキストです。  

  
 既定のスケジューラを作成するランタイムの許可と同じスケジューラを共有するすべての同時実行タスクを使用できます。 通常の機能によって提供される、[並列パターン ライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md)(PPL)、または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)並列処理を実行するために使用します。 そのため、自社のポリシーや有効期間を制御するスケジューラを直接操作する必要はありません。 PPL またはエージェント ライブラリを使用する場合、ランタイムは、存在しないため、各コンテキストの現在のスケジューラは、その場合、既定のスケジューラを作成します。 ときにスケジューラを作成して、ランタイムでは、そのスケジューラを使用して、タスクをスケジュールし、現在のスケジューラとして設定します。 特定のスケジューリング ポリシーを必要とするときにのみ、追加のスケジューラ インスタンスを作成します。 スケジューラに関連付けられているポリシーの詳細については、次を参照してください。[スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="managing"></a> スケジューラ インスタンスの有効期間を管理します。  
 ランタイム機構を使用して、参照カウントの有効期間を制御する`Scheduler`オブジェクト。  
  

 使用すると、`CurrentScheduler::Create`メソッドまたは`Scheduler::Create`メソッドを作成、`Scheduler`オブジェクト、ランタイムは、いずれかにそのスケジューラの初期の参照カウントを設定します。 ランタイムが呼び出す場合は、参照カウントをインクリメント、 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach)メソッドです。 `Scheduler::Attach`メソッド関連付けます、`Scheduler`と共に、現在のコンテキスト オブジェクト。 これにより、現在のスケジューラ。 呼び出すと、`CurrentScheduler::Create`メソッドは、両方の実行時の作成、`Scheduler`オブジェクトし現在のコンテキストにアタッチ (および参照カウントを 1 に設定)。 使用することも、 [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference)の参照カウントをインクリメントするメソッド、`Scheduler`オブジェクト。  
  
 参照カウントを呼び出すとランタイム デクリメント、 [::detach](reference/currentscheduler-class.md#detach)を現在のスケジューラをデタッチするメソッドを呼び出したり、 [concurrency::Scheduler::Release](reference/scheduler-class.md#release)メソッドです。 参照カウントが 0 になったときに、ランタイムの破棄、`Scheduler`オブジェクトがすべてのタスクの完了をスケジュールします。 実行中のタスクは、現在のスケジューラの参照カウントをインクリメントが許可されます。 したがって、参照カウントが 0 になったタスクの参照カウントをインクリメントする場合は、ランタイムは破棄されません、`Scheduler`オブジェクトの参照カウントは、0 をもう一度に到達すると、すべてのタスクを完了します。  

  
 ランタイムの内部スタックを保持する`Scheduler`各コンテキストのオブジェクト。 呼び出すと、`Scheduler::Attach`または`CurrentScheduler::Create`メソッドをランタイムにプッシュする`Scheduler`オブジェクトを現在のコンテキスト スタックにします。 これにより、現在のスケジューラ。 呼び出すと`CurrentScheduler::Detach`ランタイムは、現在のスケジューラで現在のコンテキストに対し、スタックからポップし、現在のスケジューラと 1 つ前に設定します。  
  
 ランタイムは、スケジューラ インスタンスの有効期間を管理するいくつかの方法を提供します。 次の表では、リリース、または作成するか、スケジューラを現在のコンテキストにアタッチする各メソッドに現在のコンテキストからスケジューラをデタッチする適切なメソッドを示します。  
  
|作成するメソッドまたは attach メソッド|リリースまたは detach メソッド|  
|-----------------------------|------------------------------|  
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|  
|`Scheduler::Create`|`Scheduler::Release`|  
|`Scheduler::Attach`|`CurrentScheduler::Detach`|  
|`Scheduler::Reference`|`Scheduler::Release`|  
  
 不適切な呼び出しはリリースまたはメソッドで未定義の動作のランタイムをデタッチします。  
  
 、たとえば、PPL、既定のスケジューラを作成するランタイムを原因となる機能を使用する場合はされませんリリースまたはこのスケジューラをデタッチします。 ランタイムは、作成したすべてのスケジューラの有効期間を管理します。  
  

 ランタイムを破棄しませんので、`Scheduler`使用するすべてのタスクが完了する前に、オブジェクト、 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)メソッドまたは[concurrency::currentscheduler:。RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)通知を受信するメソッドと、`Scheduler`オブジェクトは破棄されます。 スケジュールされているすべてのタスクを待機する必要がある場合に便利ですが、`Scheduler`が終了するオブジェクト。  
  
 [[トップ](#top)]  
  
##  <a name="features"></a> メソッドと機能  
 このセクションでは、の重要なメソッドをまとめたもの、`CurrentScheduler`と`Scheduler`クラスです。  
  
 考えること、`CurrentScheduler`として現在のコンテキストで使用するためのスケジューラを作成するためのヘルパー クラス。 `Scheduler`クラスを使用して、別のコンテキストに属しているスケジューラを制御できます。  
  
 次の表に、重要なメソッドで定義されている、`CurrentScheduler`クラスです。  
  
|メソッド|説明|  
|------------|-----------------|  
|[作成します。](reference/currentscheduler-class.md#create)|作成、`Scheduler`オブジェクトを指定したポリシーを使用し、現在のコンテキストに関連付けます。|  
|[Get](reference/currentscheduler-class.md#get)|ポインターを取得、`Scheduler`現在のコンテキストに関連付けられているオブジェクト。 このメソッドの参照カウントをインクリメントしない、`Scheduler`オブジェクト。|  
|[デタッチ](reference/currentscheduler-class.md#detach)|現在のコンテキストから現在のスケジューラをデタッチし、現在のスケジューラと前の 1 つを設定します。|  
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|ランタイム設定の現在のスケジューラが破棄されるときに、イベントを登録します。|  
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|作成、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)現在のスケジューラ内のオブジェクト。|  
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|現在のスケジューラのスケジュール キューに、軽量タスクを追加します。|  
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|現在のスケジューラに関連付けられているポリシーのコピーを取得します。|  
  
 次の表に、重要なメソッドで定義されている、`Scheduler`クラスです。  
  
|メソッド|説明|  
|------------|-----------------|  
|[作成します。](reference/scheduler-class.md#create)|作成、`Scheduler`オブジェクトを指定したポリシーを使用します。|  
|[添付](reference/scheduler-class.md#attach)|関連付けます、`Scheduler`と共に、現在のコンテキスト オブジェクト。|  
|[参照](reference/scheduler-class.md#reference)|参照カウンターをインクリメント、`Scheduler`オブジェクト。|  
|[Release](reference/scheduler-class.md#release)|デクリメントの参照カウンター、`Scheduler`オブジェクト。|  
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|ランタイム設定時にイベントを登録、`Scheduler`オブジェクトは破棄されます。|  
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|作成、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)内のオブジェクト、`Scheduler`オブジェクト。|  
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|軽量タスクをスケジュール設定、`Scheduler`オブジェクト。|  
|[GetPolicy](reference/scheduler-class.md#getpolicy)|関連付けられているポリシーのコピーを取得、`Scheduler`オブジェクト。|  
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|ランタイムが既定のスケジューラを作成するときに使用するためのポリシーを設定します。|  
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|呼び出す前にアクティブだった 1 つに、既定のポリシーを復元`SetDefaultSchedulerPolicy`です。 この呼び出しの後、既定のスケジューラが作成されると、ランタイムは、スケジューラを作成するのに既定のポリシー設定を使用します。|  

  
 [[トップ](#top)]  
  
##  <a name="example"></a> 「例」  
 作成してスケジューラ インスタンスを管理する方法の基本的な例については、次を参照してください。[する方法: スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)です。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)   
 [スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)   
 [スケジュール グループ](../../parallel/concrt/schedule-groups.md)

