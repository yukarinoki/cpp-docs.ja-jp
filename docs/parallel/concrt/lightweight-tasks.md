---
title: 軽量タスク |Microsoft Docs
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
ms.openlocfilehash: 8548412436be6e505c0ea08a2991e6948496f592
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210285"
---
# <a name="lightweight-tasks"></a>軽量タスク
このドキュメントでは、軽量タスク、同時実行ランタイムでの役割について説明します。 A*軽量タスク*から直接スケジュールするタスクを`concurrency::Scheduler`または`concurrency::ScheduleGroup`オブジェクト。 軽量タスクが、Windows API に提供する関数に似ています[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)関数。 したがって、軽量タスクは、同時実行ランタイムのスケジューリング機能を使用する既存のコードを採用する場合に便利です。 同時実行ランタイム自体では、軽量タスクを使用して、非同期エージェントをスケジュールおよび非同期メッセージ ブロックの間でメッセージを送信します。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。  
  
 軽量タスクでは、非同期エージェントとタスク グループよりもオーバーヘッドが少ないを実行します。 たとえば、ランタイムは通知されず、軽量タスクが終了したとき。 さらに、ランタイムはキャッチまたは処理しない軽量タスクからスローされる例外。 例外処理と軽量タスクの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)します。  
  
 ほとんどのタスク、タスク グループなどのより堅牢な機能を使用して、並列アルゴリズムをより簡単にできるために複雑なタスクに分割より基本的なものをお勧めします。 タスク グループの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。 並列アルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。  
  
 軽量タスクを作成するには、 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)、 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask)、または[concurrency::Scheduler::ScheduleTask](reference/scheduler-class.md#scheduletask)メソッド。 軽量タスクが終了するまで待つ、シャット ダウンまたは同期メカニズムを使用して親スケジューラの待機を[concurrency::event](../../parallel/concrt/reference/event-class.md)オブジェクト。  
  
## <a name="example"></a>例  
 例については、軽量タスクを使用する既存のコードを改変する方法については、次を参照してください。[チュートリアル: 既存のコードを使用して軽量タスクを適応](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)します。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [チュートリアル: 既存のコードを改変して軽量タスクを使用する](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)

