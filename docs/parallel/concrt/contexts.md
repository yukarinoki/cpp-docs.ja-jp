---
title: コンテキスト
ms.date: 11/04/2016
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
ms.openlocfilehash: 7df75ae7c1ac2b1d8c0b73ff1f1e3f2800d559b9
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87194876"
---
# <a name="contexts"></a>コンテキスト

このドキュメントでは、同時実行ランタイム内のコンテキストの役割について説明します。 スケジューラにアタッチされるスレッドは、*実行コンテキスト*または*コンテキスト*だけと呼ばれます。 [Concurrency:: wait](reference/concurrency-namespace-functions.md#wait)関数と concurrency::[Context クラス](../../parallel/concrt/reference/context-class.md)を使用すると、コンテキストの動作を制御できます。 関数を使用して、 `wait` 指定した時間だけ現在のコンテキストを中断します。 コンテキストの `Context` ブロック、ブロック解除、および生成のタイミングをより細かく制御する必要がある場合、または現在のコンテキストをオーバーサブスクライブする場合は、クラスを使用します。

> [!TIP]
> コンカレンシー ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 タスクスケジューラはアプリケーションのパフォーマンスを微調整するのに役立ちます。そのため、同時実行ランタイムを初めて使用する場合は、[並列パターンライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェントライブラリ](../../parallel/concrt/asynchronous-agents-library.md)から始めることをお勧めします。

## <a name="the-wait-function"></a>Wait 関数

[Concurrency:: wait](reference/concurrency-namespace-functions.md#wait)関数は、指定されたミリ秒数の間、現在のコンテキストの実行を協調的に生成します。 ランタイムは、yield time を使用して他のタスクを実行します。 指定された時間が経過すると、ランタイムはコンテキストの実行をスケジュールします。 このため、 `wait` 関数は、パラメーターに指定された値よりも長い時間が経過した現在のコンテキストを中断する可能性があり `milliseconds` ます。

パラメーターに 0 (ゼロ) を渡す `milliseconds` と、他のすべてのアクティブなコンテキストに作業を実行する機会が与えられるまで、ランタイムは現在のコンテキストを中断します。 これにより、タスクを他のすべてのアクティブなタスクに対して行うことができます。

### <a name="example"></a>例

関数を使用して `wait` 現在のコンテキストを生成し、他のコンテキストを実行できるようにする例については、「[方法: スケジュールグループを使用して実行順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)」を参照してください。

## <a name="the-context-class"></a>コンテキストクラス

Concurrency::[context クラス](../../parallel/concrt/reference/context-class.md)は、実行コンテキストのプログラミングの抽象化を提供し、2つの重要な機能を提供します。現在のコンテキストを協調的にブロック、ブロック解除、および生成する機能と、現在のコンテキストをオーバーサブスクライブする機能です。

### <a name="cooperative-blocking"></a>協調ブロッキング

`Context` クラスを使用すると、現在の実行コンテキストをブロックまたは生成できます。 ブロックまたは生成は、リソースが使用できないために現在のコンテキストを続行できない場合に便利です。

[Concurrency:: Context:: Block](reference/context-class.md#block)メソッドは、現在のコンテキストをブロックします。 ブロックされているコンテキストは、ランタイムが他のタスクを実行できるように処理リソースを生成します。 [Concurrency:: Context:: ブロック解除](reference/context-class.md#unblock)メソッドは、ブロックされたコンテキストのブロックを解除します。 メソッドは、を `Context::Unblock` 呼び出したコンテキストとは異なるコンテキストから呼び出す必要があり `Context::Block` ます。 コンテキストが自身のブロックを解除しようとすると、ランタイムは[concurrency:: context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md)をスローします。

コンテキストを協調的にブロックおよびブロック解除するには、通常、 [concurrency:: context:: CurrentContext](reference/context-class.md#currentcontext)を呼び出して、現在のスレッドに関連付けられているオブジェクトへのポインターを取得 `Context` し、結果を保存します。 次に、メソッドを呼び出して `Context::Block` 、現在のコンテキストをブロックします。 その後、 `Context::Unblock` 別のコンテキストからを呼び出して、ブロックされたコンテキストのブロックを解除します。

との呼び出しの各ペアが一致している必要があり `Context::Block` `Context::Unblock` ます。 [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md) `Context::Block` メソッドまたは `Context::Unblock` メソッドが、別のメソッドに対して一致する呼び出しを行わずに連続して呼び出された場合、ランタイムは concurrency:: context_unblock_unbalanced をスローします。 ただし、を呼び出す前にを呼び出す必要はありません `Context::Block` `Context::Unblock` 。 たとえば、あるコンテキストが `Context::Unblock` 同じコンテキストに対して別のコンテキストを呼び出す前にを呼び出すと、 `Context::Block` そのコンテキストはブロック解除されたままになります。

[Concurrency:: Context:: Yield](reference/context-class.md#yield)メソッドを実行すると、ランタイムは他のタスクを実行し、コンテキストの実行を再スケジュールできるようになります。 メソッドを呼び出すと、 `Context::Block` ランタイムはコンテキストを再スケジュールしません。

#### <a name="example"></a>例

、、およびの各メソッドを使用して協調セマフォクラスを実装する例につい `Context::Block` `Context::Unblock` ては `Context::Yield` 、「[方法: コンテキストクラスを使用して協調セマフォを実装](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)する」を参照してください。

##### <a name="oversubscription"></a>オーバーサブスクリプション

既定のスケジューラは、使用可能なハードウェアスレッドと同じ数のスレッドを作成します。 *オーバーサブスクリプション*を使用して、特定のハードウェアスレッドに対して追加のスレッドを作成できます。

計算を集中的に行う操作では、オーバーサブスクリプションは通常、追加のオーバーヘッドが発生するため、拡張されません。 ただし、ディスクやネットワーク接続からのデータの読み取りなど、待機時間の長いタスクの場合、オーバーサブスクリプションによって一部のアプリケーションの全体的な効率が向上します。

> [!NOTE]
> 同時実行ランタイムによって作成されたスレッドからのみオーバーサブスクリプションを有効にします。 オーバーサブスクリプションは、ランタイムによって作成されていないスレッド (メインスレッドを含む) から呼び出された場合には効果がありません。

現在のコンテキストでオーバーサブスクリプションを有効にするには、パラメーターをに設定して[concurrency:: context:: Oversubscribe](reference/context-class.md#oversubscribe)メソッドを呼び出し `_BeginOversubscription` **`true`** ます。 同時実行ランタイムによって作成されたスレッドでオーバーサブスクリプションを有効にすると、ランタイムによって1つの追加スレッドが作成されます。 オーバーサブスクリプションを必要とするすべてのタスクが完了したら、 `Context::Oversubscribe` `_BeginOversubscription` パラメーターをに設定してを呼び出し **`false`** ます。

現在のコンテキストからオーバーサブスクリプションを複数回有効にすることができますが、有効にした回数と同じ回数だけ無効にする必要があります。 オーバーサブスクリプションも入れ子にすることができます。つまり、オーバーサブスクリプションを使用する別のタスクによって作成されたタスクは、そのコンテキストをオーバーサブスクライブすることもできます。 ただし、入れ子になったタスクとその親の両方が同じコンテキストに属している場合は、の最も外側の呼び出しによって、追加のスレッドが作成され `Context::Oversubscribe` ます。

> [!NOTE]
> オーバーサブスクリプションが有効になる前に無効になっている場合、ランタイムは[concurrency:: invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md)をスローします。

###### <a name="example"></a>例

オーバーサブスクリプションを使用して、ネットワーク接続からのデータの読み取りによって発生する待機時間をオフセットする例については、「[方法: オーバーサブスクリプションを使用して待機時間をオフセット](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)する」を参照してください。

## <a name="see-also"></a>関連項目

[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)<br/>
[方法: スケジュールグループを使用して実行順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)<br/>
[方法: コンテキストクラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)<br/>
[方法: オーバーサブスクリプションを使用して待機時間をオフセットする](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)
