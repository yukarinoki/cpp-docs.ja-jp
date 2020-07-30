---
title: '方法: 例外処理を使用して並列ループを中断する'
ms.date: 11/04/2016
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
ms.openlocfilehash: 9cf42df0926022f93633a6b5b1365ae9fc646a1a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213919"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>方法: 例外処理を使用して並列ループを中断する

このトピックでは、基本的なツリー構造の検索アルゴリズムを記述する方法について説明します。

このトピックでは、並列パターンライブラリに[おけるキャンセルの](cancellation-in-the-ppl.md)役割について説明します。 例外処理の使用は、 [concurrency:: task_group:: cancel](reference/task-group-class.md#cancel)メソッドと[concurrency:: structured_task_group:: cancel](reference/structured-task-group-class.md#cancel)メソッドを使用する場合よりも、並列処理を取り消す方法としてはあまり効率的ではありません。 ただし、例外処理を使用して作業を取り消す場合は、タスクまたは並列アルゴリズムを使用するサードパーティ製のライブラリを呼び出すときに、 `task_group` キャンセルするオブジェクトまたはオブジェクトを提供しないというシナリオがあり `structured_task_group` ます。

## <a name="example"></a>例

次の例は、 `tree` データ要素と子ノードのリストを含む基本的な型を示しています。 次のセクションでは、 `for_all` 各子ノードで処理関数を再帰的に実行するメソッドの本体について説明します。

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>例

次の例は、メソッドを示して `for_all` います。 [同時実行::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムを使用して、ツリーの各ノードで処理関数を並列に実行します。

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>例

次の例は `search_for_value` 関数で、提供された `tree` オブジェクト内で値を検索します。 この関数は、 `for_all` 指定された値を含むツリーノードが見つかったときにスローする処理関数をメソッドに渡します。

`tree`クラスがサードパーティのライブラリによって提供され、変更できないとします。 この場合、 `for_all` メソッドは `task_group` または `structured_task_group` オブジェクトを呼び出し元に提供しないため、例外処理を使用することが適切です。 そのため、作業関数は親タスクグループを直接取り消すことができません。

タスクグループに指定した作業関数が例外をスローした場合、ランタイムは、タスクグループ内のすべてのタスク (子タスクグループを含む) を停止し、まだ開始されていないすべてのタスクを破棄します。 関数は、 `search_for_value` ブロックを使用し **`try`** - **`catch`** て例外をキャプチャし、結果をコンソールに出力します。

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>例

次の例では、オブジェクトを作成 `tree` し、複数の値を並行して検索します。 関数について `build_tree` は、このトピックの後半で説明します。

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

この例では、 [concurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムを使用して、値を並列に検索します。 このアルゴリズムの詳細については、「[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)」を参照してください。

## <a name="example"></a>例

次の完全な例では、例外処理を使用して、基本的なツリー構造の値を検索します。

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `task-tree-search.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc task-tree-search**

## <a name="see-also"></a>関連項目

[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group クラス](reference/task-group-class.md)<br/>
[structured_task_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each 関数](reference/concurrency-namespace-functions.md#parallel_for_each)
