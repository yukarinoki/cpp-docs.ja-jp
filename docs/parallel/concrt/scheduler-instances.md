---
description: '詳細情報: Scheduler Instances'
title: スケジューラ インスタンス
ms.date: 11/04/2016
helpviewer_keywords:
- scheduler instances
ms.assetid: 4819365f-ef99-49cc-963e-50a2a35a8d6b
ms.openlocfilehash: a11c22815c7a73c39033e51ccf47a64ceb47a92d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188054"
---
# <a name="scheduler-instances"></a>スケジューラ インスタンス

このドキュメントでは、同時実行ランタイムにおける scheduler インスタンスの役割と、 [concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md) クラスおよび [Concurrency:: currentscheduler](../../parallel/concrt/reference/currentscheduler-class.md) クラスを使用して scheduler インスタンスを作成および管理する方法について説明します。 Scheduler インスタンスは、明示的なスケジュールポリシーを特定の種類のワークロードに関連付ける場合に便利です。 たとえば、昇格したスレッド優先順位で一部のタスクを実行するようにスケジューラ インスタンスを 1 つ作成し、他のタスクについては既定のスケジューラを使用して通常のスレッド優先順位で実行することができます。

> [!TIP]
> コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 タスクスケジューラはアプリケーションのパフォーマンスを微調整するのに役立ちます。そのため、同時実行ランタイムを初めて使用する場合は、 [並列パターンライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md) または [非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md) から始めることをお勧めします。

## <a name="sections"></a><a name="top"></a> 各項

- [Scheduler および CurrentScheduler クラス](#classes)

- [Scheduler インスタンスの作成](#creating)

- [スケジューラインスタンスの有効期間の管理](#managing)

- [メソッドと機能](#features)

- [例](#example)

## <a name="the-scheduler-and-currentscheduler-classes"></a><a name="classes"></a> Scheduler および CurrentScheduler クラス

タスクスケジューラを使用すると、アプリケーションで1つ以上の *スケジューラインスタンス* を使用して作業をスケジュールできます。 [Concurrency:: scheduler](../../parallel/concrt/reference/scheduler-class.md)クラスはスケジューラインスタンスを表し、タスクのスケジュール設定に関連する機能をカプセル化します。

スケジューラにアタッチされるスレッドは、 *実行コンテキスト* または *コンテキスト* だけと呼ばれます。 現在のコンテキストでは、いつでも1つのスケジューラをアクティブにすることができます。 アクティブなスケジューラは、 *現在のスケジューラ* とも呼ばれます。 同時実行ランタイムは、 [Concurrency:: CurrentScheduler](../../parallel/concrt/reference/currentscheduler-class.md) クラスを使用して、現在のスケジューラへのアクセスを提供します。 あるコンテキストの現在のスケジューラは、別のコンテキストの現在のスケジューラとは異なる場合があります。 ランタイムは、現在のスケジューラのプロセスレベル表現を提供しません。

通常、 `CurrentScheduler` 現在のスケジューラにアクセスするには、クラスを使用します。 クラスは、 `Scheduler` 現在のものではないスケジューラを管理する必要がある場合に便利です。

次のセクションでは、scheduler インスタンスを作成および管理する方法について説明します。 これらのタスクを示す完全な例については、「 [方法: スケジューラインスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)する」を参照してください。

[[上](#top)]

## <a name="creating-a-scheduler-instance"></a><a name="creating"></a> Scheduler インスタンスの作成

オブジェクトを作成するには、次の3つの方法があり `Scheduler` ます。

- スケジューラが存在しない場合は、ランタイム機能 (並列アルゴリズムなど) を使用して作業を実行するときに、ランタイムによって既定のスケジューラが作成されます。 既定のスケジューラは、並列処理を開始するコンテキストの現在のスケジューラになります。

- [Concurrency:: CurrentScheduler:: Create](reference/currentscheduler-class.md#create)メソッドは、 `Scheduler` 特定のポリシーを使用するオブジェクトを作成し、そのスケジューラを現在のコンテキストに関連付けます。

- [Concurrency:: Scheduler:: Create](reference/scheduler-class.md#create)メソッドでは、 `Scheduler` 特定のポリシーを使用するオブジェクトが作成されますが、現在のコンテキストに関連付けられることはありません。

ランタイムが既定のスケジューラを作成できるようにすると、すべての同時実行タスクで同じスケジューラを共有できるようになります。 通常は、並列 [パターンライブラリ](../../parallel/concrt/parallel-patterns-library-ppl.md) (PPL) または [非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md) によって提供される機能を使用して、並列処理を実行します。 そのため、スケジューラを直接操作してポリシーまたは有効期間を制御する必要はありません。 PPL またはエージェントライブラリを使用する場合、ランタイムは、既定のスケジューラが存在しない場合は既定のスケジューラを作成し、各コンテキストの現在のスケジューラにします。 スケジューラを作成し、それを現在のスケジューラとして設定すると、ランタイムはそのスケジューラを使用してタスクをスケジュールします。 特定のスケジューリングポリシーが必要な場合にのみ、追加の scheduler インスタンスを作成します。 スケジューラに関連付けられているポリシーの詳細については、「 [Scheduler policies (スケジューラポリシー](../../parallel/concrt/scheduler-policies.md))」を参照してください。

[[上](#top)]

## <a name="managing-the-lifetime-of-a-scheduler-instance"></a><a name="managing"></a> スケジューラインスタンスの有効期間の管理

ランタイムは、参照カウント機構を使用してオブジェクトの有効期間を制御し `Scheduler` ます。

`CurrentScheduler::Create`メソッドまたはメソッドを使用して `Scheduler::Create` オブジェクトを作成すると `Scheduler` 、ランタイムはそのスケジューラの最初の参照カウントを1に設定します。 ランタイムは、 [concurrency:: Scheduler:: Attach](reference/scheduler-class.md#attach) メソッドを呼び出すと、参照カウントをインクリメントします。 メソッドは、 `Scheduler::Attach` `Scheduler` オブジェクトを現在のコンテキストに関連付けます。 これにより、現在のスケジューラが作成されます。 メソッドを呼び出すと、 `CurrentScheduler::Create` ランタイムは、オブジェクトを作成 `Scheduler` し、現在のコンテキストにアタッチします (参照カウントを1に設定します)。 また、 [concurrency:: Scheduler:: reference](reference/scheduler-class.md#reference) メソッドを使用して、オブジェクトの参照カウントをインクリメントすることもでき `Scheduler` ます。

[Concurrency:: CurrentScheduler::D etach](reference/currentscheduler-class.md#detach)メソッドを呼び出して現在のスケジューラをデタッチするか、 [Concurrency:: Scheduler:: Release](reference/scheduler-class.md#release)メソッドを呼び出すと、ランタイムは参照カウントをデクリメントします。 参照カウントが0になると、すべてのスケジュールされたタスクが完了した後に、ランタイムによってオブジェクトが破棄され `Scheduler` ます。 実行中のタスクは、現在のスケジューラの参照カウントをインクリメントできます。 したがって、参照カウントがゼロに達し、タスクが参照カウントをインクリメントした場合、 `Scheduler` 参照カウントが再び0になり、すべてのタスクが終了するまで、ランタイムはオブジェクトを破棄しません。

ランタイムは、コンテキストごとにオブジェクトの内部スタックを保持し `Scheduler` ます。 メソッドまたはメソッドを呼び出すと、 `Scheduler::Attach` `CurrentScheduler::Create` ランタイムはその `Scheduler` オブジェクトを現在のコンテキストのスタックにプッシュします。 これにより、現在のスケジューラが作成されます。 を呼び出すと `CurrentScheduler::Detach` 、ランタイムは現在のコンテキストのスタックから現在のスケジューラをポップし、前のスケジューラを現在のスケジューラとして設定します。

ランタイムには、スケジューラインスタンスの有効期間を管理するためのいくつかの方法が用意されています。 次の表は、現在のコンテキストに対してスケジューラを作成またはアタッチする各メソッドの現在のコンテキストから、スケジューラを解放またはデタッチするための適切なメソッドを示しています。

|Create または attach メソッド|Release または detach メソッド|
|-----------------------------|------------------------------|
|`CurrentScheduler::Create`|`CurrentScheduler::Detach`|
|`Scheduler::Create`|`Scheduler::Release`|
|`Scheduler::Attach`|`CurrentScheduler::Detach`|
|`Scheduler::Reference`|`Scheduler::Release`|

不適切な release メソッドまたは detach メソッドを呼び出すと、ランタイムで特定できない動作が発生します。

ランタイムが既定のスケジューラを作成するなどの機能を使用する場合は、このスケジューラを解放したり、デタッチしたりしないでください。 ランタイムは、作成するスケジューラの有効期間を管理します。

すべてのタスクが完了する前にランタイムによってオブジェクトが破棄されるわけではないため `Scheduler` 、 [concurrency:: Scheduler:: RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent) メソッドまたは [Concurrency:: Currentscheduler:: RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent) メソッドを使用して、 `Scheduler` オブジェクトが破棄されたときに通知を受け取ることができます。 これは、オブジェクトによってスケジュールされたすべてのタスクが終了するまで待機する必要がある場合に便利です `Scheduler` 。

[[上](#top)]

## <a name="methods-and-features"></a><a name="features"></a> メソッドと機能

このセクションでは、クラスとクラスの重要なメソッドについて説明し `CurrentScheduler` `Scheduler` ます。

クラスは、 `CurrentScheduler` 現在のコンテキストで使用するスケジューラを作成するためのヘルパーと考えてください。 `Scheduler`クラスを使用すると、別のコンテキストに属するスケジューラを制御できます。

次の表は、クラスによって定義される重要なメソッドを示して `CurrentScheduler` います。

|Method|説明|
|------------|-----------------|
|[作成](reference/currentscheduler-class.md#create)|`Scheduler`指定されたポリシーを使用するオブジェクトを作成し、現在のコンテキストに関連付けます。|
|[Get](reference/currentscheduler-class.md#get)|`Scheduler`現在のコンテキストに関連付けられているオブジェクトへのポインターを取得します。 このメソッドは、オブジェクトの参照カウントをインクリメントしません `Scheduler` 。|
|[[デタッチ]](reference/currentscheduler-class.md#detach)|現在のコンテキストから現在のスケジューラをデタッチし、前のスケジューラを現在のスケジューラとして設定します。|
|[RegisterShutdownEvent](reference/currentscheduler-class.md#registershutdownevent)|現在のスケジューラが破棄されたときにランタイムによって設定されるイベントを登録します。|
|[CreateScheduleGroup](reference/currentscheduler-class.md#createschedulegroup)|現在のスケジューラに [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) オブジェクトを作成します。|
|[ScheduleTask](reference/currentscheduler-class.md#scheduletask)|現在のスケジューラのスケジュールキューに軽量タスクを追加します。|
|[GetPolicy](reference/currentscheduler-class.md#getpolicy)|現在のスケジューラに関連付けられているポリシーのコピーを取得します。|

次の表は、クラスによって定義される重要なメソッドを示して `Scheduler` います。

|Method|説明|
|------------|-----------------|
|[作成](reference/scheduler-class.md#create)|`Scheduler`指定されたポリシーを使用するオブジェクトを作成します。|
|[[アタッチ]](reference/scheduler-class.md#attach)|オブジェクトを `Scheduler` 現在のコンテキストに関連付けます。|
|[参照](reference/scheduler-class.md#reference)|オブジェクトの参照カウンターをインクリメントし `Scheduler` ます。|
|[リリース](reference/scheduler-class.md#release)|オブジェクトの参照カウンターをデクリメントし `Scheduler` ます。|
|[RegisterShutdownEvent](reference/scheduler-class.md#registershutdownevent)|オブジェクトが破棄されるときにランタイムによって設定されるイベントを登録し `Scheduler` ます。|
|[CreateScheduleGroup](reference/scheduler-class.md#createschedulegroup)|オブジェクトに [concurrency:: ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md) オブジェクトを作成し `Scheduler` ます。|
|[ScheduleTask](reference/scheduler-class.md#scheduletask)|オブジェクトから軽量タスクをスケジュール `Scheduler` します。|
|[GetPolicy](reference/scheduler-class.md#getpolicy)|オブジェクトに関連付けられているポリシーのコピーを取得 `Scheduler` します。|
|[SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)|ランタイムが既定のスケジューラを作成するときに使用するポリシーを設定します。|
|[ResetDefaultSchedulerPolicy](reference/scheduler-class.md#resetdefaultschedulerpolicy)|既定のポリシーを、の呼び出しの前にアクティブだったものに復元 `SetDefaultSchedulerPolicy` します。 この呼び出しの後に既定のスケジューラが作成された場合、ランタイムは既定のポリシー設定を使用してスケジューラを作成します。|

[[上](#top)]

## <a name="example"></a><a name="example"></a> 「例」

スケジューラインスタンスを作成および管理する方法の基本的な例については、「 [方法: スケジューラインスタンスを管理](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: スケジューラインスタンスを管理する](../../parallel/concrt/how-to-manage-a-scheduler-instance.md)<br/>
[スケジューラポリシー](../../parallel/concrt/scheduler-policies.md)<br/>
[スケジュールグループ](../../parallel/concrt/schedule-groups.md)
