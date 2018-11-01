---
title: 'チュートリアル: 既存のコードを改変して軽量タスクを使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- using lightweight tasks [Concurrency Runtime]
- lightweight tasks, using [Concurrency Runtime]
ms.assetid: 1edfe818-d274-46de-bdd3-e92967c9bbe0
ms.openlocfilehash: a0e724ff6f43dc0c888e787350f4841f14383f14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50654503"
---
# <a name="walkthrough-adapting-existing-code-to-use-lightweight-tasks"></a>チュートリアル: 既存のコードを改変して軽量タスクを使用する

ここでは、Windows API を使用する既存のコードを改変して、軽量タスクを使用するスレッドを作成および実行する方法について説明します。

A*軽量タスク*から直接スケジュールするタスクを[concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)または[concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)オブジェクト。 軽量タスクは、既存のコードを改変してコンカレンシー ランタイムのスケジュール機能を使用する場合に有用です。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前にトピックを読んで、[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。

## <a name="example"></a>例

### <a name="description"></a>説明

Windows API を使用してスレッドを作成および実行する一般的な方法を次の例に示します。 この例では、 [CreateThread](/windows/desktop/api/processthreadsapi/nf-processthreadsapi-createthread)関数を呼び出す、`MyThreadFunction`別のスレッドでします。

### <a name="code"></a>コード

[!code-cpp[concrt-windows-threads#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_1.cpp)]

### <a name="comments"></a>コメント

この例を実行すると、次の出力が生成されます。

```Output
Parameters = 50, 100
```

コンカレンシー ランタイムを使用して同じタスクを実行するようにこのコード例を改変する手順を次に示します。

### <a name="to-adapt-the-example-to-use-a-lightweight-task"></a>軽量タスクを使用するように例を改変するには

1. ヘッダー ファイル concrt.h の `#include` ディレクティブを追加します。

[!code-cpp[concrt-migration-lwt#2](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_2.cpp)]

1. `using` 名前空間の `concurrency` ディレクティブを追加します。

[!code-cpp[concrt-migration-lwt#3](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_3.cpp)]

1. `MyThreadFunction` の宣言を次のように変更して、`__cdecl` 呼び出し規則を使用すると共に、`void` を返します。

[!code-cpp[concrt-migration-lwt#4](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_4.cpp)]

1. 変更、`MyData`構造に含まれる、 [concurrency::event](../../parallel/concrt/reference/event-class.md)タスクが完了したことをメイン アプリケーションに通知するオブジェクト。

[!code-cpp[concrt-migration-lwt#5](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_5.cpp)]

1. 呼び出しに置き換えます`CreateThread`を呼び出して、 [concurrency::CurrentScheduler::ScheduleTask](reference/currentscheduler-class.md#scheduletask)メソッド。

[!code-cpp[concrt-migration-lwt#6](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_6.cpp)]

1. 呼び出しに置き換えます`WaitForSingleObject`を呼び出して、 [concurrency::event::wait](reference/event-class.md#wait)メソッドがタスクの完了を待機します。

[!code-cpp[concrt-migration-lwt#7](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_7.cpp)]

1. `CloseHandle` 呼び出しを削除します。

1. 手順 3. に合わせて、`MyThreadFunction` の定義のシグネチャを変更します。

[!code-cpp[concrt-migration-lwt#8](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_8.cpp)]

9. 最後に、`MyThreadFunction`関数を呼び出し、 [concurrency::event::set](reference/event-class.md#set)タスクが完了したことをメイン アプリケーションに通知するメソッド。

[!code-cpp[concrt-migration-lwt#9](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_9.cpp)]

10. `return` ステートメントを `MyThreadFunction` から削除します。

## <a name="example"></a>例

### <a name="description"></a>説明

次の完成版の例に、軽量タスクを使用して `MyThreadFunction` 関数を呼び出すためのコードを示します。

### <a name="code"></a>コード

[!code-cpp[concrt-migration-lwt#1](../../parallel/concrt/codesnippet/cpp/walkthrough-adapting-existing-code-to-use-lightweight-tasks_10.cpp)]

### <a name="comments"></a>コメント

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[Scheduler クラス](../../parallel/concrt/reference/scheduler-class.md)
