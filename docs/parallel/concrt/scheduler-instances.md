---
title: スケジューラ インスタンス
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: 19bd871857dcef6aaef153798388c0272239fa1f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180168"
---
# <a name="scheduler-instances"></a>スケジューラ インスタンス

このドキュメントで使用する方法と、同時実行ランタイム スケジューラ インスタンスの役割を説明します、 [concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)と[:currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md)クラスを作成および管理するにはスケジューラ インスタンス。 スケジューラ インスタンスは、特定の種類のワークロードに明示的なスケジューリング ポリシーを関連付ける場合に便利です。 たとえば、昇格したスレッド優先順位で一部のタスクを実行するようにスケジューラ インスタンスを 1 つ作成し、他のタスクについては既定のスケジューラを使用して通常のスレッド優先順位で実行することができます。

> [!TIP]
>  コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

##  <a name="top"></a> セクション

- [スケジューラと CurrentScheduler クラス](#classes)

- [スケジューラ インスタンスを作成します。](#creating)

- [スケジューラ インスタンスの有効期間を管理します。](#managing)

- [メソッドと機能](#features)

- [例](#example)

##  <a name="classes"></a> スケジューラと CurrentScheduler クラス

タスク スケジューラにより、アプリケーションが 1 つまたは複数を使用する*スケジューラ インスタンス*作業をスケジュールします。 [Concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)クラスは、スケジューラ インスタンスを表すし、タスクのスケジューリングに関連する機能をカプセル化します。

スケジューラに関連付けられているスレッドと呼ばれる、*実行コンテキスト*、または単*コンテキスト*します。 1 つのスケジューラは、いつでも、現在のコンテキストでアクティブにできます。 アクティブなスケジューラとも呼ばれますが、*現在のスケジューラ*します。 同時実行ランタイムを使用して、 [:currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md)クラスを現在のスケジューラにアクセスできるようにします。 1 つのコンテキストの現在のスケジューラは、別のコンテキストの現在のスケジューラと異なることができます。 ランタイムは、現在のスケジューラのプロセス レベルの表現を提供しません。

通常、`CurrentScheduler`クラスは、現在のスケジューラへのアクセスに使用されます。 `Scheduler`クラスは、現在ではないスケジューラを管理する必要がある場合に便利です。

次のセクションでは、作成してスケジューラ インスタンスを管理する方法について説明します。 これらのタスクを示す完全な例を参照してください[方法。スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)します。

[[トップ](#top)]

##  <a name="creating"></a> スケジューラ インスタンスを作成します。

これら 3 つの方法を作成する、`Scheduler`オブジェクト。

- スケジューラが存在しない場合、ランタイムは、ランタイム機能、たとえば、並列アルゴリズムを使用して作業を実行する場合の既定のスケジューラを作成します。 既定のスケジューラでは、並列処理を開始するコンテキストの現在のスケジューラになります。

- [::Create](reference/currentscheduler-class.md#create)メソッドを作成、`Scheduler`オブジェクトを特定のポリシーを使用し、そのスケジューラを現在のコンテキストに関連付けます。

- [:Create](reference/scheduler-class.md#create)メソッドを作成、`Scheduler`オブジェクトを特定のポリシーを使用しますが、現在のコンテキストは関連付けできません。

同じスケジューラを共有するすべての同時実行タスクにより、ランタイムが既定のスケジューラを作成することができます。 によって提供される機能では、通常、[並列パターン ライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md)(PPL)、または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)並列処理を実行するために使用します。 そのため、そのポリシーまたは有効期間を制御するスケジューラを直接操作する必要はありません。 PPL またはエージェント ライブラリを使用する場合、ランタイムは、各コンテキストの現在のスケジューラになりますが存在しない場合、既定のスケジューラを作成します。 スケジューラを作成し、ランタイムでは、そのスケジューラを使用して、タスクをスケジュールし、現在のスケジューラとして設定します。 特定のスケジューリング ポリシーを必要とする場合にのみ、追加のスケジューラ インスタンスを作成します。 スケジューラに関連付けられているポリシーの詳細については、次を参照してください。[スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)します。

[[トップ](#top)]

##  <a name="managing"></a> スケジューラ インスタンスの有効期間を管理します。

ランタイムでは、参照カウントのメカニズムを使用して、有効期間を制御`Scheduler`オブジェクト。

使用すると、`CurrentScheduler::Create`メソッドまたは`Scheduler::Create`を作成する方法、`Scheduler`オブジェクト、ランタイムは、いずれかにそのスケジューラの初期の参照カウントを設定します。 ランタイムが呼び出すときに、参照カウントをインクリメント、 [concurrency::Scheduler::Attach](reference/scheduler-class.md#attach)メソッド。 `Scheduler::Attach`メソッドに関連付け、`Scheduler`と共に、現在のコンテキスト オブジェクト。 これにより、現在のスケジューラ。 呼び出すと、 `CurrentScheduler::Create` 、メソッドは、ランタイムを作成、`Scheduler`オブジェクトし現在のコンテキストにアタッチします (および参照カウントを 1 に設定)。 使用することも、 [concurrency::Scheduler::Reference](reference/scheduler-class.md#reference)の参照カウントをインクリメントするメソッド、`Scheduler`オブジェクト。

参照カウントを呼び出すと、ランタイム デクリメント、 [:currentscheduler](reference/currentscheduler-class.md#detach)現在のスケジューラをデタッチするメソッドを呼び出したり、 [concurrency::Scheduler::Release](reference/scheduler-class.md#release)メソッド。 参照カウントがゼロに達すると、ランタイムの破棄、`Scheduler`オブジェクトがすべてのタスクの完了をスケジュールします。 実行中のタスクは現在のスケジューラの参照カウントをインクリメントできます。 そのため、参照カウントがゼロになるし、タスクは、参照カウントをインクリメント、ランタイムを破棄しません、`Scheduler`オブジェクトの参照カウントは、0 をもう一度に到達すると、すべてのタスクを完了します。

ランタイムの内部のスタックを保持する`Scheduler`各コンテキストのオブジェクト。 呼び出すと、`Scheduler::Attach`または`CurrentScheduler::Create`したメソッド、ランタイムがプッシュ`Scheduler`オブジェクトを現在のコンテキスト スタックにします。 これにより、現在のスケジューラ。 呼び出すと`CurrentScheduler::Detach`ランタイムは、現在のコンテキスト スタックから現在のスケジューラをポップし、現在のスケジューラとしては、前の設定。

ランタイムは、スケジューラ インスタンスの有効期間を管理するためにいくつかの方法を提供します。 次の表では、解放または作成するか、スケジューラを現在のコンテキストにアタッチする各メソッドの現在のコンテキストからスケジューラをデタッチする適切なメソッドを示します。

|作成またはアタッチする方法|リリースまたはデタッチ メソッド|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

不適切な呼び出しはリリースまたはメソッドで未定義の動作のランタイムをデタッチします。

、たとえば、PPL、既定のスケジューラを作成するランタイムを原因となる機能を使用する場合はいないリリースまたはデタッチこのスケジューラ。 ランタイムは、作成したすべてのスケジューラの有効期間を管理します。

ランタイムを破棄しませんので、`Scheduler`使用するオブジェクトのすべてのタスクが完了する前に、 [concurrency::Scheduler::RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)メソッドまたは[:currentscheduler:。RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)メソッド通知を受信するときに、`Scheduler`オブジェクトは破棄されます。 スケジュールされているすべてのタスクを待つ必要がある場合に便利ですが、`Scheduler`終了するオブジェクト。

[[トップ](#top)]

##  <a name="features"></a> メソッドと機能

このセクションでは、の重要なメソッドをまとめたものです、`CurrentScheduler`と`Scheduler`クラス。

考える、`CurrentScheduler`として現在のコンテキストで使用するためのスケジューラを作成するためのヘルパー クラス。 `Scheduler`クラスを使用して、別のコンテキストに属しているスケジューラを制御できます。

次の表に、重要なメソッドで定義されている、`CurrentScheduler`クラス。

|メソッド|説明|
|------------|-----------------|
|[作成](reference/currentscheduler-class.md#create)|作成、`Scheduler`オブジェクトを指定したポリシーを使用し、現在のコンテキストに関連付けます。|
|[Get](reference/currentscheduler-class.md#get)|ポインターを取得、`Scheduler`現在のコンテキストに関連付けられているオブジェクト。 このメソッドの参照カウントをインクリメントしていない、`Scheduler`オブジェクト。|
|[Detach](reference/currentscheduler-class.md#detach)|現在のコンテキストから現在のスケジューラをデタッチし、現在のスケジューラとして 1 つ前を設定します。|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|現在のスケジューラが破棄されるときに、ランタイムが設定されるイベントを登録します。|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|作成、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)現在のスケジューラ内のオブジェクト。|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|現在のスケジューラのスケジュール キューには、軽量タスクを追加します。|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|現在のスケジューラに関連付けられているポリシーのコピーを取得します。|

次の表に、重要なメソッドで定義されている、`Scheduler`クラス。

|メソッド|説明|
|------------|-----------------|
|[作成](reference/scheduler-class.md#create)|作成、`Scheduler`オブジェクトを指定したポリシーを使用します。|
|[Attach](reference/scheduler-class.md#attach)|関連付けます、`Scheduler`と共に、現在のコンテキスト オブジェクト。|
|[参照](reference/scheduler-class.md#reference)|参照カウンターをインクリメント、`Scheduler`オブジェクト。|
|[Release](reference/scheduler-class.md#release)|デクリメントの参照カウンター、`Scheduler`オブジェクト。|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|ときに、ランタイムが設定されるイベントを登録、`Scheduler`オブジェクトは破棄されます。|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|作成、 [concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)オブジェクト、`Scheduler`オブジェクト。|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|軽量タスクをスケジュール、`Scheduler`オブジェクト。|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|関連付けられているポリシーのコピーを取得、`Scheduler`オブジェクト。|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|ランタイムが既定のスケジューラを作成するときに使用するためのポリシーを設定します。|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|呼び出す前にアクティブだった 1 つに、既定のポリシーを復元`SetDefaultSchedulerPolicy`します。 この呼び出しの後、既定のスケジューラが作成される場合、ランタイムは、スケジューラを作成する既定のポリシー設定を使用します。|

[[トップ](#top)]

##  <a name="example"></a> 「例」

作成してスケジューラ インスタンスを管理する方法の基本的な例については、次を参照してください。[方法。スケジューラ インスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)します。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: スケジューラ インスタンスを管理する](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[スケジューラ ポリシー](../../parallel/concrt/scheduler-policies.md)<br/>
[スケジュール グループ](../../parallel/concrt/schedule-groups.md)
