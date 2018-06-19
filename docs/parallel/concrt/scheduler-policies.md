---
title: スケジューラ ポリシー |Microsoft ドキュメント
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
ms.openlocfilehash: 7d9c855260df34290d01f1eeeee89e8bfe8988de
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690408"
---
# <a name="scheduler-policies"></a>スケジューラ ポリシー
このドキュメントでは、同時実行ランタイム スケジューラ ポリシーの役割について説明します。 A*スケジューラ ポリシー*スケジューラがタスクを管理するときに使用する方法を制御します。 たとえば、一部のタスクで実行を必要とするアプリケーション`THREAD_PRIORITY_NORMAL`およびその他のタスクで実行する`THREAD_PRIORITY_HIGHEST`です。  2 つのスケジューラ インスタンスを作成することができます: いずれかを指定する、`ContextPriority`ポリシーが`THREAD_PRIORITY_NORMAL`もう 1 つを同じポリシーを指定する`THREAD_PRIORITY_HIGHEST`です。  
  
 スケジューラ ポリシーを使用するは、使用可能な処理リソースを分割し、各スケジューラにリソースの固定セットを割り当てます。 たとえば、4 つのプロセッサに対応する並列アルゴリズムを検討してください。 4 つ以下のプロセッサを同時に使用するには、そのタスクを制限するスケジューラ ポリシーを作成することができます。  
  
> [!TIP]
>  同時実行ランタイムでは、既定のスケジューラを提供します。 そのため、アプリケーションで 1 つを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
 使用すると、 [concurrency::CurrentScheduler::Create](reference/currentscheduler-class.md#create)、 [:create](reference/scheduler-class.md#create)、または[concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)メソッドを提供する、スケジューラ インスタンスを作成、 [concurrency::schedulerpolicy](../../parallel/concrt/reference/schedulerpolicy-class.md)スケジューラの動作を指定するキー/値ペアのコレクションを格納するオブジェクト。 `SchedulerPolicy`コンス トラクターは、可変個の引数を受け取ります。 最初の引数を指定しようとしているポリシー要素の数です。 残りの引数は、ポリシー要素ごとのキーと値のペアです。 次の例を作成、`SchedulerPolicy`ポリシーの 3 つの要素を指定するオブジェクト。 ランタイムは、指定されていないポリシー キーの既定値を使用します。  

  
 [!code-cpp[concrt-scheduler-policy#2](../../parallel/concrt/codesnippet/cpp/scheduler-policies_1.cpp)]  
  

 [Concurrency::PolicyElementKey](reference/concurrency-namespace-enums.md#policyelementkey)列挙体は、タスク スケジューラに関連付けられているポリシー キーを定義します。 次の表は、ポリシーのキーと、それぞれのランタイムで使用される既定値について説明します。  
  
|ポリシー キー|説明|既定値|  
|----------------|-----------------|-------------------|  
|`SchedulerKind`|A [concurrency::SchedulerType](reference/concurrency-namespace-enums.md#schedulertype)タスクのスケジュール設定に使用するスレッドの種類を指定する値。|`ThreadScheduler` (通常のスレッドを使用)。 これは、このキーの唯一の有効な値です。|  
|`MaxConcurrency`|`unsigned int`スケジューラが使用する同時実行リソースの最大数を指定する値。|[concurrency::MaxExecutionResources](reference/concurrency-namespace-constants1.md#maxexecutionresources)|  
|`MinConcurrency`|`unsigned int`スケジューラが使用する同時実行リソースの最小数を指定する値。|`1`|  
|`TargetOversubscriptionFactor`|`unsigned int`処理の各リソースに割り当てるスレッドの数を指定する値。|`1`|  
|`LocalContextCacheSize`|`unsigned int`各仮想プロセッサのローカル キューでキャッシュできるコンテキストの最大数を指定する値。|`8`|  
|`ContextStackSize`|`unsigned int` (キロバイト単位)、各コンテキスト用に予約するスタックのサイズを指定する値。|`0` (既定のスタック サイズを使用)|  
|`ContextPriority`|`int`各コンテキストのスレッドの優先度を指定する値。 これに渡すことができる任意の値を指定できます[SetThreadPriority](http://msdn.microsoft.com/library/windows/desktop/ms686277)または`INHERIT_THREAD_PRIORITY`です。|`THREAD_PRIORITY_NORMAL`|  

|`SchedulingProtocol`|A [concurrency::SchedulingProtocolType](reference/concurrency-namespace-enums.md#schedulingprotocoltype)を使用するスケジューリング アルゴリズムを指定する値です |。`EnhanceScheduleGroupLocality`|  
|`DynamicProgressFeedback`|A [concurrency::DynamicProgressFeedbackType](reference/concurrency-namespace-enums.md#dynamicprogressfeedbacktype)進行状況の統計情報に基づく情報に従って、リソースを再配分するかどうかを指定する値。<br /><br /> **注**にこのポリシーを設定しないで`ProgressFeedbackDisabled`ランタイムで使用するために予約されているためです |。`ProgressFeedbackEnabled`|  

  
 各スケジューラは、タスクをスケジュールするときに、独自のポリシーを使用します。 1 つのスケジューラに関連付けられているポリシーは、その他のスケジューラの動作には影響しません。 作成した後に、スケジューラ ポリシーを変更することはできませんさらに、`Scheduler`オブジェクト。  
  
> [!IMPORTANT]
>  スケジューラ ポリシーのみを使用すると、ランタイムは、作成スレッドの属性を制御できます。 スレッドの関係または未定義の動作が発生する可能性がありますので、ランタイムによって作成されるスレッドの優先順位は変わりません。  
  
 ランタイムは、明示的に作成しないいずれかの場合に、既定のスケジューラを作成します。 かどうか、アプリケーションで、既定のスケジューラを使用する必要しますが、呼び出しを使用するには、そのスケジューラ ポリシーを指定する、 [concurrency::Scheduler::SetDefaultSchedulerPolicy](reference/scheduler-class.md#setdefaultschedulerpolicy)メソッド並列処理をスケジュールする前にします。 呼び出さない場合、`Scheduler::SetDefaultSchedulerPolicy`メソッドは、テーブルから値を既定のポリシー ランタイム使用します。  
  
 使用して、 [concurrency::CurrentScheduler::GetPolicy](reference/currentscheduler-class.md#getpolicy)と[concurrency::Scheduler::GetPolicy](reference/scheduler-class.md#getpolicy)スケジューラ ポリシーのコピーを取得するメソッド。 これらのメソッドから受信したポリシー値スケジューラを作成するときに指定するポリシー値と異なることができます。  
  
## <a name="example"></a>例  
 スケジューラの動作を制御する特定のスケジューラ ポリシーを使用する例を検証するを参照してください[する方法: 特定のスケジューラ ポリシーの指定](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)と[する方法: エージェントを使用して特定のスケジューラ ポリシーを作成します](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: 特定のスケジューラ ポリシーを指定します。](../../parallel/concrt/how-to-specify-specific-scheduler-policies.md)   
 [方法: 特定のスケジューラ ポリシーを使用するエージェントを作成する](../../parallel/concrt/how-to-create-agents-that-use-specific-scheduler-policies.md)

