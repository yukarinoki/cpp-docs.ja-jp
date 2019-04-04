---
title: 軽量タスク
ms.date: 11/04/2016
helpviewer_keywords:
- lightweight tasks
ms.assetid: b6dcfc7a-9fa9-4144-96a6-2845ea272017
ms.openlocfilehash: 19918cf73c2b5b03db895c4751b22b1666ce01de
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57326687"
---
# <a name="lightweight-tasks"></a>軽量タスク

このドキュメントでは、軽量タスク、同時実行ランタイムでの役割について説明します。 A*軽量タスク*から直接スケジュールするタスクを`concurrency::Scheduler`または`concurrency::ScheduleGroup`オブジェクト。 軽量タスクが、Windows API に提供する関数に似ています[CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)関数。 したがって、軽量タスクは、同時実行ランタイムのスケジューリング機能を使用する既存のコードを採用する場合に便利です。 同時実行ランタイム自体では、軽量タスクを使用して、非同期エージェントをスケジュールおよび非同期メッセージ ブロックの間でメッセージを送信します。

> [!TIP]
>  コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

軽量タスクでは、非同期エージェントとタスク グループよりもオーバーヘッドが少ないを実行します。 たとえば、ランタイムは通知されず、軽量タスクが終了したとき。 さらに、ランタイムはキャッチまたは処理しない軽量タスクからスローされる例外。 例外処理と軽量タスクの詳細については、[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)を参照してください。

ほとんどのタスク、タスク グループなどのより堅牢な機能を使用して、並列アルゴリズムをより簡単にできるために複雑なタスクに分割より基本的なものをお勧めします。 タスク グループの詳細については、[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)を参照してください。 並列アルゴリズムの詳細については、[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)を参照してください。

軽量タスクを作成するには、 [concurrency::ScheduleGroup::ScheduleTask](reference/schedulegroup-class.md#scheduletask)、 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask)、または[concurrency::Scheduler::ScheduleTask](reference/scheduler-class.md#scheduletask)メソッド。 軽量タスクが終了するまで待つ、シャット ダウンまたは同期メカニズムを使用して親スケジューラの待機を[concurrency::event](../../parallel/concrt/reference/event-class.md)オブジェクト。

## <a name="example"></a>例

例については、軽量タスクを使用する既存のコードを改変する方法については、次を参照してください。[チュートリアル。軽量タスクを使用する既存のコードを適合させる](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)します。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[チュートリアル: 既存のコードを改変して軽量タスクを使用する](../../parallel/concrt/walkthrough-adapting-existing-code-to-use-lightweight-tasks.md)
