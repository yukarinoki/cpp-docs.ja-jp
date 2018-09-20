---
title: スケジューラ ポリシー |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- scheduler policies
ms.assetid: 58fb68bd-4a57-40a8-807b-6edb6f083cd9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cabb35901dab38247e8af7909199f8c7efdb4020
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442956"
---
# <a name="scheduler-policies"></a>スケジューラ ポリシー

このドキュメントでは、同時実行ランタイム スケジューラ ポリシーの役割について説明します。 A*スケジューラ ポリシー*スケジューラがタスクを管理する場合に使用する方法を制御します。 たとえば、いくつかのタスクで実行する必要のあるアプリケーション`THREAD_PRIORITY_NORMAL`およびその他のタスクで実行する`THREAD_PRIORITY_HIGHEST`します。  2 つのスケジューラ インスタンスを作成することができます。 いずれかを指定する、`ContextPriority`ポリシーが`THREAD_PRIORITY_NORMAL`別に同じポリシーを指定すると`THREAD_PRIORITY_HIGHEST`。

スケジューラ ポリシーを使用するは、使用可能な処理リソースを分割して、各スケジューラにリソースの固定セットを割り当てます。 たとえば、4 つのプロセッサに対応する並列アルゴリズムを検討してください。 4 つ以下のプロセッサを同時に使用するには、そのタスクを制限するスケジューラ ポリシーを作成することができます。

> [!TIP]
>  同時実行ランタイムでは、既定のスケジューラを提供します。 そのため、アプリケーションで 1 つを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

使用すると、 [::create](reference/currentscheduler-class.md#create)、 [:create](reference/scheduler-class.md#create)、または[concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)指定したスケジューラ インスタンスを作成する方法、 [concurrency::schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)スケジューラの動作を指定するキー/値ペアのコレクションを格納するオブジェクト。 `SchedulerPolicy`コンス トラクターは可変個の引数を受け取ります。 最初の引数には、ポリシーの要素を指定しようとしている数です。 残りの引数は、各ポリシー要素のキーと値のペアです。 次の例では、作成、`SchedulerPolicy`ポリシーの 3 つの要素を指定するオブジェクト。 ランタイムでは、指定されていないポリシー キーの既定値が使用されます。

[!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]

[Concurrency::PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey)列挙型は、タスク スケジューラに関連付けられているポリシーのキーを定義します。 次の表では、ポリシーのキーとそれぞれのランタイムが使用する既定値について説明します。

|ポリシー キー|説明|既定値|
|----------------|-----------------|-------------------|
|`SchedulerKind`|A [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype)タスクのスケジュール設定に使用するスレッドの種類を指定する値。|`ThreadScheduler` (通常のスレッドを使用)。 これは、このキーの唯一の有効な値です。|
|`MaxConcurrency`|`unsigned int`スケジューラを使用する同時実行リソースの最大数を指定する値。|[concurrency::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|
|`MinConcurrency`|`unsigned int`スケジューラを使用して同時実行リソースの最小数を指定する値。|`1`|
|`TargetOversubscriptionFactor`|`unsigned int`処理の各リソースに割り当てるスレッドの数を指定する値。|`1`|
|`LocalContextCacheSize`|`unsigned int`仮想プロセッサあたりのローカル キューでキャッシュ可能なコンテキストの最大数を示す値。|`8`|
|`ContextStackSize`|`unsigned int`各コンテキスト用に予約する (キロバイト単位)、スタックのサイズを指定する値。|`0` (既定のスタック サイズを使用)|
|`ContextPriority`|`int`各コンテキストのスレッドの優先順位を指定する値。 渡すことができる任意の値を指定できます[SetThreadPriority](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-setthreadpriority)または`INHERIT_THREAD_PRIORITY`します。|`THREAD_PRIORITY_NORMAL`|

|`SchedulingProtocol`|A [concurrency::SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype)を使用するスケジューリング アルゴリズムを指定する値 |。`EnhanceScheduleGroupLocality`| |`DynamicProgressFeedback`|A [concurrency::DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype)進行状況の統計情報に基づく情報に従ってリソースを再調整するかどうかを指定する値。<br /><br /> **注**このポリシーを設定しないでください`ProgressFeedbackDisabled`ランタイムで使用するために予約されているためです |。`ProgressFeedbackEnabled`|

各スケジューラは、タスクをスケジュールするときに、独自のポリシーを使用します。 1 つのスケジューラに関連付けられているポリシーでは、その他のすべてのスケジューラの動作は影響しません。 作成した後に、スケジューラ ポリシーを変更することはできませんさらに、`Scheduler`オブジェクト。

> [!IMPORTANT]
>  スケジューラ ポリシーのみを使用すると、ランタイムは、作成スレッドの属性を制御できます。 スレッド アフィニティまたは未定義の動作が発生する可能性がありますので、ランタイムによって作成されるスレッドの優先順位は変更されません。

ランタイムは、明示的に作成しない 1 つである場合の既定のスケジューラを作成します。 アプリケーションでは、既定のスケジューラを使用したいが、呼び出しを使用するには、そのスケジューラ ポリシーを指定するかどうか、 [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)メソッドを並列処理をスケジュールする前にします。 呼び出さない場合、`Scheduler::SetDefaultSchedulerPolicy`メソッドは、既定のポリシー値をテーブルから、ランタイムは使用できます。

使用して、 [concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy)と[concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy)スケジューラ ポリシーのコピーを取得するメソッド。 これらのメソッドから受信したポリシーの値は、スケジューラを作成するときに指定するポリシー値とは異なることができます。

## <a name="example"></a>例

スケジューラの動作を制御する特定のスケジューラ ポリシーを使用する例を検証するを参照してください[する方法: 特定のスケジューラ ポリシーの指定](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)と[する方法: エージェントを使用して特定のスケジューラ ポリシーを作成します](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: 特定のスケジューラ ポリシーを指定する](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)<br/>
[方法: 特定のスケジューラ ポリシーを使用するエージェントを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

