---
title: コンテキスト |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- contexts [Concurrency Runtime]
ms.assetid: 10c1d861-8fbb-4ba0-b2ec-61876b11176e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a8297c8a7a779140f6464f39491e73950ddaeeb
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="contexts"></a>コンテキスト

このドキュメントでは、同時実行ランタイムのコンテキストの役割について説明します。 スケジューラにアタッチされているスレッドと呼ばれる、*実行コンテキスト*、または単*コンテキスト*です。 [Concurrency::wait](reference/concurrency-namespace-functions.md#wait)関数と、同時実行制御::[コンテキスト クラス](../../parallel/concrt/reference/context-class.md)を使用すると、コンテキストの動作を制御します。 使用して、`wait`関数を指定した時間、現在のコンテキストを中断します。 使用して、`Context`時、現在のコンテキストをオーバーサブスク ライブしたい場合やコンテキスト ブロック、ブロックを解除すると yield より詳細に制御する必要があります。  
  
> [!TIP]
>  同時実行ランタイムには既定のスケジューラが用意されているため、アプリケーションにスケジューラを作成する必要はありません。 始めることをお勧めタスク スケジューラを使用してアプリケーションのパフォーマンスを微調整できますが、ため、[並列パターン ライブラリ (PPL)](../../parallel/concrt/parallel-patterns-library-ppl.md)または[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)場合同時実行ランタイムに新しいです。  
  
## <a name="the-wait-function"></a>Wait 関数  

 [Concurrency::wait](reference/concurrency-namespace-functions.md#wait)関数が協調的に指定したミリ秒数の現在のコンテキストの実行を譲歩します。 ランタイムでは、yield 時間を使用して、その他のタスクを実行します。 指定した時間が経過すると、ランタイム スケジュールの実行コンテキストを変更します。 したがって、`wait`関数は、現在のコンテキストに指定された値よりも長いを中断可能性があります、`milliseconds`パラメーター。  
  
 0 (ゼロ) を渡す、`milliseconds`を他のすべてのアクティブなコンテキストで作業を実行する機会が与えられますまで、現在のコンテキストを中断するランタイムを発生させます。 これにより、他のすべてのアクティブなタスクに対してタスクを譲渡することができます。  
  
### <a name="example"></a>例  
 使用する例については、 `wait` 、現在のコンテキストを生成する関数を実行しを参照してください、他のコンテキストを許可してしまう[する方法: スケジュール グループの順序の実行に影響を使用する](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)です。  
  
## <a name="the-context-class"></a>Context クラス  
 同時実行性::[コンテキスト クラス](../../parallel/concrt/reference/context-class.md)実行コンテキストのプログラミングの抽象化して 2 つの重要な機能を提供しています: 協調的ブロック、ブロック解除、および現在のコンテキストを生成する機能と、権限を許可する現在のコンテキストをオーバーサブスク ライブされます。  
  
### <a name="cooperative-blocking"></a>協調ブロッキング  
 `Context` クラスを使用すると、現在の実行コンテキストをブロックまたは生成できます。 ブロックまたは生成は、リソースが利用できないため、現在のコンテキストを続行できないとき便利です。  
  

 [Concurrency::Context::Block](reference/context-class.md#block)メソッドは、現在のコンテキストをブロックします。 ブロックされているコンテキストは、ランタイムはその他のタスクを実行できるように、処理リソースを生成します。 [Concurrency::Context::Unblock](reference/context-class.md#unblock)メソッド ブロックされているコンテキストのブロックを解除します。 `Context::Unblock`と呼ばれるものとは異なるコンテキストからメソッドを呼び出す必要があります`Context::Block`です。 ランタイムは、スロー [concurrency::context_self_unblock](../../parallel/concrt/reference/context-self-unblock-class.md)場合は、コンテキストはそれ自体のブロックを解除しようとしています。  
  
 呼び出す通常の協調的なブロックは、コンテキストのブロックを解除[concurrency::Context::CurrentContext](reference/context-class.md#currentcontext)へのポインターを取得する、`Context`結果を保存および現在のスレッドに関連付けられているオブジェクト。 呼び出して、`Context::Block`メソッドを現在のコンテキストをブロックします。 その後、呼び出す`Context::Unblock`ブロックされているコンテキストのブロックを解除する別のコンテキストから。  
  
 呼び出しの各ペアに一致する必要があります`Context::Block`と`Context::Unblock`です。 ランタイムは、スロー [concurrency::context_unblock_unbalanced](../../parallel/concrt/reference/context-unblock-unbalanced-class.md)ときに、`Context::Block`または`Context::Unblock`メソッドは、その他のメソッドに一致する呼び出しがない連続して呼び出されます。 ただし、呼び出す必要はありません`Context::Block`を呼び出す前に`Context::Unblock`です。 たとえば、1 つのコンテキストでは`Context::Unblock`別のコンテキスト呼び出される前に`Context::Block`同じコンテキストではそのコンテキストがブロックされていません。  
  
 [:Yield](reference/context-class.md#yield)ランタイムが他のタスクを実行して、コンテキストの実行のスケジュールを変更できるように、メソッドが実行を譲歩します。 呼び出すと、`Context::Block`メソッドをランタイムにコンテキストが再スケジュールされません。  

  
#### <a name="example"></a>例  
 使用する例については、 `Context::Block`、 `Context::Unblock`、および`Context::Yield`協調セマフォ クラスを実装するメソッドを参照してください[する方法: Context クラスを使用して協調セマフォを実装する](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)です。  
  
##### <a name="oversubscription"></a>オーバーサブスクリプション  
 既定のスケジューラには、使用可能なハードウェア スレッドが同じ数のスレッドが作成されます。 使用することができます*オーバー サブスクリプション*の特定のハードウェア スレッドの他のスレッドを作成します。  
  
 負荷の高い計算操作は、オーバー サブスクリプション通常拡張しませんによるオーバーヘッドが発生します。 ただしの待機時間の時間が長いタスク、たとえば、ディスクやネットワーク接続からデータを読み取りオーバー サブスクリプションを使用効率を向上できます全体的な一部のアプリケーション。  
  
> [!NOTE]
>  同時実行ランタイムによって作成されたスレッドからのみオーバー サブスクリプションを有効にします。 (メイン スレッドを含む)、ランタイムによって作成されていないスレッドから呼び出された場合は、オーバー サブスクリプションを指定しても効果はありません。  
  
 現在のコンテキストでオーバー サブスクリプションを有効にするを呼び出して、 [concurrency::Context::Oversubscribe](reference/context-class.md#oversubscribe)メソッドを`_BeginOversubscription`パラメーターに設定`true`です。 同時実行ランタイムによって作成されたスレッドでオーバー サブスクリプションを有効にすると、1 つの追加のスレッドを作成するランタイムが行われます。 オーバー サブスクリプション終了日を必要とするすべてのタスクの後に呼び出す`Context::Oversubscribe`で、`_BeginOversubscription`パラメーターに設定`false`です。  

  
 複数回から現在のコンテキストでは、オーバー サブスクリプションを有効にすることができますが、有効にする同じ回数を無効にする必要があります。 オーバー サブスクリプションも入れ子になんだことができます。つまり、オーバー サブスクリプションを使用する別のタスクによって作成されるタスクは、そのコンテキストをオーバーサブスク ライブできますも。 ただし、入れ子になったタスクとその親の両方に属する場合は、同じコンテキスト、最も外側の呼び出しのみ`Context::Oversubscribe`に追加のスレッドを作成します。  
  
> [!NOTE]
>  ランタイムは、スロー [concurrency::invalid_oversubscribe_operation](../../parallel/concrt/reference/invalid-oversubscribe-operation-class.md)を有効にする前に、オーバー サブスクリプションが無効になっている場合。  
  
###### <a name="example"></a>例  
 例については、ネットワーク接続からデータを読み取るが原因で発生する待機時間のオフセットにオーバー サブスクリプションを使用する、次を参照してください。[する方法: を使用して、オーバー サブスクリプション待機時間のオフセットを](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)です。  
  
## <a name="see-also"></a>関連項目  
 [タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)   
 [方法: スケジュール グループを使用して、実行の順序に影響を与える](../../parallel/concrt/how-to-use-schedule-groups-to-influence-order-of-execution.md)   
 [方法: Context クラスを使用して協調セマフォを実装するには](../../parallel/concrt/how-to-use-the-context-class-to-implement-a-cooperative-semaphore.md)   
 [方法: オーバーサブスクリプションを使用して待機時間を短縮する](../../parallel/concrt/how-to-use-oversubscription-to-offset-latency.md)

