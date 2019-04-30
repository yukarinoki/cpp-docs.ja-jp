---
title: 'チュートリアル: COM 対応アプリケーションで同時実行ランタイムの使用'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 9d306377be4a000c54fb5556b15263a15b2d4618
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62407785"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>チュートリアル: COM 対応アプリケーションで同時実行ランタイムの使用

このドキュメントでは、コンポーネント オブジェクト モデル (COM) を使用するアプリケーションでコンカレンシー ランタイムを使用する方法について説明します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM の詳細については、次を参照してください。[コンポーネント オブジェクト モデル (COM)](/windows/desktop/com/component-object-model--com--portal)します。

## <a name="managing-the-lifetime-of-the-com-library"></a>COM ライブラリの有効期間の管理

コンカレンシー ランタイムでの COM の使用は他のコンカレンシー機構と同じ基本原則に従いますが、これらのライブラリを組み合わせて効率よく使用するには次のガイドラインが役に立ちます。

- スレッドを呼び出す必要があります[CoInitializeEx](/windows/desktop/api/combaseapi/nf-combaseapi-coinitializeex) COM ライブラリを使用する前にします。

- スレッドでは、同じ引数を毎回提供する場合に限り、`CoInitializeEx` を複数回呼び出すことができます。

- 呼び出しごとに`CoInitializeEx`、スレッドが呼び出す必要がありますも[CoUninitialize](/windows/desktop/api/combaseapi/nf-combaseapi-couninitialize)します。 つまり、`CoInitializeEx` と `CoUninitialize` の呼び出しは、均等化する必要があります。

- あるスレッド アパートメントから別のアパートメントに切り替えるには、スレッドは新しいスレッド処理仕様で `CoInitializeEx` を呼び出す前に、COM ライブラリを完全に解放する必要があります。

コンカレンシー ランタイムで COM を使用する場合は、COM に関する他の基本原則が適用されます。 たとえば、オブジェクトをシングルスレッド アパートメント (STA: Single-Threaded Apartment) に作成し、そのオブジェクトを別のアパートメントにマーシャリングするアプリケーションでは、受信メッセージを処理するためのメッセージ ループも提供する必要があります。 また、アパートメント間でオブジェクトをマーシャリングすると、パフォーマンスが低下する可能性があることに注意してください。

### <a name="using-com-with-the-parallel-patterns-library"></a>並列パターン ライブラリでの COM の使用

タスク グループや並列アルゴリズムなど、並列パターン ライブラリ (PPL) のコンポーネントで COM を使用するときは、各タスクまたは反復処理の間に COM ライブラリを使用する前に `CoInitializeEx` を呼び出し、各タスクまたは反復処理が終了する前に `CoUninitialize` を呼び出します。 次の例では、COM ライブラリの有効期間を管理する方法を示しています、 [concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)オブジェクト。

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

タスクまたは並列アルゴリズムを取り消すとき、またはタスクの本体で例外をスローするときは、COM ライブラリが正しく解放されていることを確認する必要があります。 呼び出し、作業することを保証するのには`CoUninitialize`セッションを終了する前に使用して、`try-finally`ブロックまたは*Resource Acquisition Is Initialization* (RAII) パターンです。 次の例では、`try-finally` ブロックを使用して、タスクが終了するとき、取り消されるとき、または例外がスローされるときに、COM ライブラリを解放しています。

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

次の例では、RAII パターンを使用して、特定のスコープでの COM ライブラリの有効期間を管理する `CCoInitializer` クラスを定義しています。

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

`CCoInitializer` クラスを使用すると、次のように、タスクが終了するときに COM ライブラリを自動的に解放できます。

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

同時実行ランタイムでの取り消し処理の詳細については、次を参照してください。 [PPL における取り消し処理](cancellation-in-the-ppl.md)します。

### <a name="using-com-with-asynchronous-agents"></a>非同期エージェントでの COM の使用

非同期エージェントで COM を使用するときに呼び出す`CoInitializeEx`で COM ライブラリを使用する前に、 [concurrency::agent::run](reference/agent-class.md#run)エージェントのメソッド。 その後、`CoUninitialize` メソッドが返される前に `run` を呼び出します。 コンス トラクターまたはデストラクターが、エージェントのでは COM 管理ルーチンを使用しないと、オーバーライドしない場合、 [:start](reference/agent-class.md#start)または[concurrency::agent:: 終了](reference/agent-class.md#done)メソッドのため、これらのメソッドは異なるスレッドから呼び出される、`run`メソッド。

次の例では、`CCoAgent` という名前の基本的なエージェント クラスを示します。このクラスは `run` メソッドで COM ライブラリを管理します。

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

詳細な例については、このチュートリアルで後ほど説明します。

### <a name="using-com-with-lightweight-tasks"></a>軽量タスクでの COM の使用

ドキュメント[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)軽量タスク、同時実行ランタイムでの役割について説明します。 Windows API で `CreateThread` 関数に渡すスレッド ルーチンと同じように、軽量タスクで COM を使用できます。 これを次の例に示します。

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM 対応のアプリケーションの例

このセクションを使用する完全な COM 対応アプリケーションを示しています、 `IScriptControl` 、n を計算するスクリプトを実行するインターフェイス<sup>th</sup>フィボナッチ数。 この例では、最初にメイン スレッドからスクリプトを呼び出した後、PPL とエージェントを使用してスクリプトを同時に呼び出します。

次のようなヘルパー関数 `RunScriptProcedure` を使用します。この関数は、`IScriptControl` オブジェクトのプロシージャを呼び出します。

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

`wmain`関数を作成、`IScriptControl`オブジェクトに、n を計算するスクリプト コードを追加します。<sup>th</sup>フィボナッチ数を呼び出し、その後、`RunScriptProcedure`そのスクリプトを実行する関数。

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL からのスクリプトの呼び出し

次の関数では、`ParallelFibonacci`を使用して、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムを並列でスクリプトを呼び出します。 この関数は、`CCoInitializer` クラスを使用して、タスクの反復ごとの COM ライブラリの有効期間を管理します。

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

この例で `ParallelFibonacci` 関数を使用するには、`wmain` 関数が返される前に次のコードを追加します。

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>エージェントからのスクリプトの呼び出し

次の例は、`FibonacciScriptAgent`クラスで、n を計算するスクリプト プロシージャを呼び出す<sup>th</sup>フィボナッチ数。 `FibonacciScriptAgent` クラスは、メッセージ パッシングを使用して、スクリプト関数への入力値をメイン プログラムから受け取ります。 `run` メソッドは、タスク全体を通じて COM ライブラリの有効期間を管理します。

[!code-cpp[concrt-parallel-scripts#11](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_11.cpp)]

次の `AgentFibonacci` 関数は、複数の `FibonacciScriptAgent` オブジェクトを作成し、メッセージ パッシングを使用して複数の入力値をこれらのオブジェクトに送ります。

[!code-cpp[concrt-parallel-scripts#12](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_12.cpp)]

この例で `AgentFibonacci` 関数を使用するには、`wmain` 関数が返される前に次のコードを追加します。

[!code-cpp[concrt-parallel-scripts#13](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_13.cpp)]

### <a name="the-complete-example"></a>完全な例

並列アルゴリズムと非同期エージェントを使用してフィボナッチ数列を計算するスクリプト プロシージャを呼び出す、完全なコード例を次に示します。

[!code-cpp[concrt-parallel-scripts#14](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_14.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Main Thread:
fib(15) = 610

Parallel Fibonacci:
fib(15) = 610
fib(10) = 55
fib(16) = 987
fib(18) = 2584
fib(11) = 89
fib(17) = 1597
fib(19) = 4181
fib(12) = 144
fib(13) = 233
fib(14) = 377

Agent Fibonacci:
fib(30) = 832040
fib(22) = 17711
fib(10) = 55
fib(12) = 144
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`parallel-scripts.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc parallel-scripts.cpp/link ole32.lib**

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)<br/>
[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
