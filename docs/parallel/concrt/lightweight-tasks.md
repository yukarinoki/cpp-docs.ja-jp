---
title: 軽量タスク |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d602f83cfe2da6bc1506e07720d3ef021ebce04a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="lightweight-tasks"></a>軽量タスク
このドキュメントでは、軽量タスク、同時実行ランタイムでの役割について説明します。 A*軽量タスク*から直接スケジュールするタスク、`concurrency::Scheduler`または`concurrency::ScheduleGroup`オブジェクト。 軽量タスクが Windows API に提供する関数に似た[CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453)関数。 したがって、軽量タスクは、同時実行ランタイムのスケジュール機能を使用する既存のコードを改変する場合に役立ちます。 同時実行ランタイム自体では、軽量タスクを使用して、非同期エージェントをスケジュールし、非同期メッセージ ブロックの間でメッセージを送信します。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
 軽量タスクは、非同期エージェントやタスク グループよりもオーバーヘッドが少ないを実行します。 たとえば、ランタイムは通知されず、軽量タスクが終了したとき。 さらに、ランタイムはキャッチまたは処理は、軽量タスクからスローされる例外。 例外処理や軽量タスクの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)です。  
  
 ほとんどのタスク、タスク グループなどのより堅牢な機能を使用して、並列アルゴリズムができるためより簡単に複雑なタスクに分割より基本的なものをお勧めします。 タスク グループの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。 並列アルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
 軽量タスクを作成するには、 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)、 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask)、または[concurrency::Scheduler::ScheduleTask](reference/scheduler-class.md#scheduletask)メソッドです。 軽量タスクが終了するまで待つ、シャット ダウンまたはなどの同期機構を使用する親スケジューラの待機、 [concurrency::event](../../parallel/concrt/reference/event-class.md)オブジェクト。  
  
## <a name="example"></a>例  
 例については、軽量タスクを使用する既存のコードを改変する方法については、次を参照してください。[チュートリアル: 既存のコードを使用して軽量タスクを適応させる](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)です。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [チュートリアル: 既存のコードを改変して軽量タスクを使用する](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

