---
description: '詳細については、「チュートリアル: COM-Enabled アプリケーションでの同時実行ランタイムの使用」を参照してください。'
title: 'チュートリアル: COM 対応アプリケーションでのコンカレンシー ランタイムの使用'
ms.date: 04/25/2019
helpviewer_keywords:
- Concurrency Runtime, use with COM
- COM, use with the Concurrency Runtime
ms.assetid: a7c798b8-0fc8-4bee-972f-22ef158f7f48
ms.openlocfilehash: 1844062531a9cc4e0b7bb8864fc8d8343063d75a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150099"
---
# <a name="walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application"></a>チュートリアル: COM 対応アプリケーションでのコンカレンシー ランタイムの使用

このドキュメントでは、コンポーネント オブジェクト モデル (COM) を使用するアプリケーションでコンカレンシー ランタイムを使用する方法について説明します。

## <a name="prerequisites"></a>前提条件

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)

- [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)

COM の詳細については、「 [Component Object Model (com)](/windows/win32/com/component-object-model--com--portal)」を参照してください。

## <a name="managing-the-lifetime-of-the-com-library"></a>COM ライブラリの有効期間の管理

コンカレンシー ランタイムでの COM の使用は他のコンカレンシー機構と同じ基本原則に従いますが、これらのライブラリを組み合わせて効率よく使用するには次のガイドラインが役に立ちます。

- スレッドは、COM ライブラリを使用する前に [CoInitializeEx](/windows/win32/api/combaseapi/nf-combaseapi-coinitializeex) を呼び出す必要があります。

- スレッドでは、同じ引数を毎回提供する場合に限り、`CoInitializeEx` を複数回呼び出すことができます。

- を呼び出すたびに `CoInitializeEx` 、スレッドは [CoUninitialize](/windows/win32/api/combaseapi/nf-combaseapi-couninitialize)も呼び出す必要があります。 つまり、`CoInitializeEx` と `CoUninitialize` の呼び出しは、均等化する必要があります。

- あるスレッド アパートメントから別のアパートメントに切り替えるには、スレッドは新しいスレッド処理仕様で `CoInitializeEx` を呼び出す前に、COM ライブラリを完全に解放する必要があります。

コンカレンシー ランタイムで COM を使用する場合は、COM に関する他の基本原則が適用されます。 たとえば、オブジェクトをシングルスレッド アパートメント (STA: Single-Threaded Apartment) に作成し、そのオブジェクトを別のアパートメントにマーシャリングするアプリケーションでは、受信メッセージを処理するためのメッセージ ループも提供する必要があります。 また、アパートメント間でオブジェクトをマーシャリングすると、パフォーマンスが低下する可能性があることに注意してください。

### <a name="using-com-with-the-parallel-patterns-library"></a>並列パターン ライブラリでの COM の使用

タスク グループや並列アルゴリズムなど、並列パターン ライブラリ (PPL) のコンポーネントで COM を使用するときは、各タスクまたは反復処理の間に COM ライブラリを使用する前に `CoInitializeEx` を呼び出し、各タスクまたは反復処理が終了する前に `CoUninitialize` を呼び出します。 次の例は、 [concurrency:: structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md) オブジェクトを使用して COM ライブラリの有効期間を管理する方法を示しています。

[!code-cpp[concrt-parallel-scripts#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_1.cpp)]

タスクまたは並列アルゴリズムを取り消すとき、またはタスクの本体で例外をスローするときは、COM ライブラリが正しく解放されていることを確認する必要があります。 タスクが終了する前にを確実に呼び出すに `CoUninitialize` は、ブロックを使用する `try-finally` か、 *リソースの取得を初期化* (RAII) パターンにします。 次の例では、`try-finally` ブロックを使用して、タスクが終了するとき、取り消されるとき、または例外がスローされるときに、COM ライブラリを解放しています。

[!code-cpp[concrt-parallel-scripts#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_2.cpp)]

次の例では、RAII パターンを使用して、特定のスコープでの COM ライブラリの有効期間を管理する `CCoInitializer` クラスを定義しています。

[!code-cpp[concrt-parallel-scripts#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_3.cpp)]

`CCoInitializer` クラスを使用すると、次のように、タスクが終了するときに COM ライブラリを自動的に解放できます。

[!code-cpp[concrt-parallel-scripts#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_4.cpp)]

同時実行ランタイムでのキャンセルの詳細については、「 [PPL でのキャンセル](cancellation-in-the-ppl.md)」を参照してください。

### <a name="using-com-with-asynchronous-agents"></a>非同期エージェントでの COM の使用

非同期エージェントで COM を使用する場合は、 `CoInitializeEx` エージェントに対して [concurrency:: agent:: run](reference/agent-class.md#run) メソッドで com ライブラリを使用する前に、を呼び出します。 その後、`CoUninitialize` メソッドが返される前に `run` を呼び出します。 COM 管理ルーチンは、エージェントのコンストラクターまたはデストラクターでは使用せず、 [concurrency:: agent:: start](reference/agent-class.md#start) または [concurrency:: agent::d 1 つ](reference/agent-class.md#done) のメソッドをオーバーライドしないでください。これらのメソッドは、メソッドとは異なるスレッドから呼び出されます `run` 。

次の例では、`CCoAgent` という名前の基本的なエージェント クラスを示します。このクラスは `run` メソッドで COM ライブラリを管理します。

[!code-cpp[concrt-parallel-scripts#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_5.cpp)]

詳細な例については、このチュートリアルで後ほど説明します。

### <a name="using-com-with-lightweight-tasks"></a>軽量タスクでの COM の使用

ドキュメント [タスクスケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md) では、同時実行ランタイム内の軽量タスクの役割について説明します。 Windows API で `CreateThread` 関数に渡すスレッド ルーチンと同じように、軽量タスクで COM を使用できます。 次の例を参照してください。

[!code-cpp[concrt-parallel-scripts#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_6.cpp)]

## <a name="an-example-of-a-com-enabled-application"></a>COM 対応のアプリケーションの例

このセクションでは、インターフェイスを使用して `IScriptControl` n<sup>番目</sup> のフィボナッチ数列を計算するスクリプトを実行する完全な COM 対応アプリケーションについて説明します。 この例では、最初にメイン スレッドからスクリプトを呼び出した後、PPL とエージェントを使用してスクリプトを同時に呼び出します。

次のようなヘルパー関数 `RunScriptProcedure` を使用します。この関数は、`IScriptControl` オブジェクトのプロシージャを呼び出します。

[!code-cpp[concrt-parallel-scripts#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_7.cpp)]

関数は、 `wmain` オブジェクトを作成し `IScriptControl` 、n<sup>番目</sup> のフィボナッチ数を計算するスクリプトコードを追加して、その `RunScriptProcedure` スクリプトを実行する関数を呼び出します。

[!code-cpp[concrt-parallel-scripts#8](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_8.cpp)]

### <a name="calling-the-script-from-the-ppl"></a>PPL からのスクリプトの呼び出し

次の関数は、 `ParallelFibonacci` [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムを使用して、スクリプトを並列で呼び出します。 この関数は、`CCoInitializer` クラスを使用して、タスクの反復ごとの COM ライブラリの有効期間を管理します。

[!code-cpp[concrt-parallel-scripts#9](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_9.cpp)]

この例で `ParallelFibonacci` 関数を使用するには、`wmain` 関数が返される前に次のコードを追加します。

[!code-cpp[concrt-parallel-scripts#10](../../parallel/concrt/codesnippet/cpp/walkthrough-using-the-concurrency-runtime-in-a-com-enabled-application_10.cpp)]

### <a name="calling-the-script-from-an-agent"></a>エージェントからのスクリプトの呼び出し

次の例は、 `FibonacciScriptAgent` n<sup>番目</sup> のフィボナッチ数列を計算するスクリプトプロシージャを呼び出すクラスを示しています。 `FibonacciScriptAgent` クラスは、メッセージ パッシングを使用して、スクリプト関数への入力値をメイン プログラムから受け取ります。 `run` メソッドは、タスク全体を通じて COM ライブラリの有効期間を管理します。

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

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `parallel-scripts.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc parallel-scripts (/link)**

## <a name="see-also"></a>関連項目

[同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)<br/>
[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)
