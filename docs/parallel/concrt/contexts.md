---
title: コンテキスト
ms.date: 11/04/2016
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
ms.openlocfilehash: d511f8fa751d61c3c490a184dae660096dd9f76f
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57285907"
---
# <a name="contexts"></a>コンテキスト

このドキュメントでは、同時実行ランタイムのコンテキストの役割について説明します。 スケジューラに関連付けられているスレッドと呼ばれる、*実行コンテキスト*、または単*コンテキスト*します。 [Concurrency::wait](reference/concurrency-namespace-functions.md#wait)関数と、同時実行::[コンテキスト クラス](../../parallel/concrt/reference/context-class.md)コンテキストの動作を制御できます。 使用して、`wait`関数を指定した時間、現在のコンテキストを中断します。 使用して、`Context`クラス経由で、現在のコンテキストをオーバーサブスク ライブするときにコンテキスト ブロック、ブロックを解除し生成、または詳細に制御する必要があります。

> [!TIP]
>  コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 開始するので、タスク スケジューラを使用してアプリケーションのパフォーマンスを微調整する、推奨、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[Asynchronous Agents Library](../../parallel/concrt/asynchronous-agents-library.md)場合新しい同時実行ランタイムにします。

## <a name="the-wait-function"></a>Wait 関数

[Concurrency::wait](reference/concurrency-namespace-functions.md#wait)関数が指定したミリ秒数の現在のコンテキストの実行を協調的になります。 ランタイムでは、yield 時間を使用して、その他のタスクを実行します。 指定した時間が経過すると、ランタイム スケジュールの実行コンテキストを変更します。 そのため、`wait`関数は、現在のコンテキストに指定された値よりも長い中断可能性があります、`milliseconds`パラメーター。

0 (ゼロ) を渡す、`milliseconds`パラメーターとその他のすべてのアクティブなコンテキストで作業を実行する機会が与えられますまで、現在のコンテキストを中断するランタイム。 その他のすべてのアクティブなタスクにタスクを譲渡できます。

### <a name="example"></a>例

使用する例については、 `wait` 、現在のコンテキストを生成する関数を確認を実行するには、その他のコンテキストを許可してしまう[方法。スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)します。

## <a name="the-context-class"></a>Context クラス

同時実行性::[コンテキスト クラス](../../parallel/concrt/reference/context-class.md)実行コンテキストのプログラミングの抽象化して 2 つの重要な機能を提供しています: 協調的ブロック、ブロック解除、および現在のコンテキストを生成する機能と機能現在のコンテキストをオーバーサブスク ライブされます。

### <a name="cooperative-blocking"></a>協調ブロッキング


  `Context` クラスを使用すると、現在の実行コンテキストをブロックまたは生成できます。 リソースが利用できないため、現在のコンテキストを続行できない場合、ブロックまたは生成する機能は便利です。

[Concurrency::Context::Block](reference/context-class.md#block)メソッドは、現在のコンテキストをブロックします。 ブロックされているコンテキストでは、ランタイムは、その他のタスクを実行できるように、処理リソースが生成されます。 [Concurrency::Context::Unblock](reference/context-class.md#unblock)メソッド ブロックされているコンテキストのブロックを解除します。 `Context::Unblock`と呼ばれるものとは異なるコンテキストからメソッドを呼び出す必要があります`Context::Block`します。 ランタイムによってスロー [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md)コンテキスト自体のブロックを解除しようとするとします。

呼び出す通常の協調をブロックし、コンテキストのブロックを解除、 [concurrency::Context::CurrentContext](reference/context-class.md#currentcontext)へのポインターを取得する、`Context`と結果を保存、現在のスレッドに関連付けられているオブジェクト。 呼び出して、`Context::Block`メソッドは、現在のコンテキストをブロックします。 後で、呼び出す`Context::Unblock`ブロックされているコンテキストのブロックを解除する別のコンテキストから。

呼び出しの各ペアに一致する必要があります`Context::Block`と`Context::Unblock`します。 ランタイムによってスロー [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md)ときに、`Context::Block`または`Context::Unblock`メソッドが他のメソッドに一致する呼び出しがない連続して呼び出されます。 ただし、呼び出す必要はない`Context::Block`を呼び出す前に`Context::Unblock`します。 たとえば、1 つのコンテキストでは`Context::Unblock`別のコンテキストの呼び出しの前に`Context::Block`同じコンテキストではそのコンテキストがブロックされていません。

[:Yield](reference/context-class.md#yield)メソッドは実行をランタイムの他のタスクを実行してコンテキストの実行のスケジュールを変更できるようにします。 呼び出すと、`Context::Block`メソッド、ランタイムが、コンテキストを再スケジュールします。

#### <a name="example"></a>例

使用する例については、 `Context::Block`、 `Context::Unblock`、および`Context::Yield`協調セマフォ クラスを実装するメソッドを参照してください[方法。コンテキスト クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)します。

##### <a name="oversubscription"></a>オーバーサブスクリプション

既定のスケジューラは、使用可能なハードウェア スレッドが同じ数のスレッドを作成します。 使用することができます*オーバー サブスクリプション*の特定のハードウェア スレッドの追加のスレッドを作成します。

負荷の高い操作では、オーバー サブスクリプション通常はスケーラビリティの追加のオーバーヘッドが発生します。 ただし、長い待機時間があるタスクでは、たとえば、ディスクやネットワーク接続からデータを読み取るオーバー サブスクリプション効率を向上できます全体的な一部のアプリケーションの。

> [!NOTE]
>  同時実行ランタイムによって作成されたスレッドからのみオーバー サブスクリプションを有効にします。 (メイン スレッドを含む)、ランタイムによって作成されていないスレッドから呼び出された場合は、オーバー サブスクリプションを指定しても効果はありません。

現在のコンテキストでオーバー サブスクリプションを有効にする、 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe)メソッドを`_BeginOversubscription`パラメーターに設定**true**します。 同時実行ランタイムによって作成されたスレッドでオーバー サブスクリプションを有効にすると、1 つ追加のスレッドを作成するランタイムが行われます。 オーバー サブスクリプションの終了日を必要とするすべてのタスクの後に呼び出す`Context::Oversubscribe`で、`_BeginOversubscription`パラメーターに設定**false**します。

複数回から現在のコンテキストでは、オーバー サブスクリプションを有効にすることができますが、有効にしたのと同じ回数で無効にする必要があります。 オーバー サブスクリプションも入れ子になんだことができます。つまり、オーバー サブスクリプションを使用して別のタスクによって作成されるタスクは、そのコンテキストをオーバーサブスク ライブできますも。 ただし、入れ子になったタスクとその親の両方が同じコンテキストに最も外側の呼び出しだけに属している場合`Context::Oversubscribe`追加のスレッドを作成します。

> [!NOTE]
>  ランタイムによってスロー [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md)が有効にする前に、オーバー サブスクリプションが無効になっている場合。

###### <a name="example"></a>例

オーバー サブスクリプションを使用して、ネットワーク接続からデータを読み取ることによって発生した待機時間を短縮する例を参照してください[方法。オーバー サブスクリプションを使用して、待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)します。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: スケジュール グループを使用して実行順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[方法: Context クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[方法: オーバーサブスクリプションを使用して待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)
