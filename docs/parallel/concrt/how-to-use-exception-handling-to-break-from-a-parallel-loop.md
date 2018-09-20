---
title: '方法: 並列ループから処理を中断する例外を使用して |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- search algorithm, writing [Concurrency Runtime]
- writing a search algorithm [Concurrency Runtime]
ms.assetid: 16d7278c-2d10-4014-9f58-f1899e719ff9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a15910885b26c8026a6e504ef36d492cf63445e8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379828"
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>方法: 例外処理を使用して並列ループを中断する

このトピックでは、基本的なツリー構造の検索アルゴリズムを記述する方法を示します。

トピック[キャンセル](cancellation-in-the-ppl.md)並列パターン ライブラリでキャンセルの役割について説明します。 例外処理の使用は小さい効率的に使用するよりも並列処理の取り消し、 [concurrency::task_group::cancel](reference/task-group-class.md#cancel)と[::structured_task_group::cancel](reference/structured-task-group-class.md#cancel)メソッド。 ただし、処理を取り消す例外処理の使用が適したシナリオの 1 つは、タスクまたは並列アルゴリズムを使用して、提供されませんが、サードパーティ ライブラリを呼び出すときに、`task_group`または`structured_task_group`をキャンセルするオブジェクト。

## <a name="example"></a>例

次の例では、基本的な`tree`データ要素と子ノードのリストを含む型。 次のセクションの本文を表示する、`for_all`メソッドを再帰的には、各子ノードに処理関数を実行します。

[!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]

## <a name="example"></a>例

次の例は、`for_all`メソッド。 使用して、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)並列ツリーの各ノードに処理関数を実行するアルゴリズム。

[!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]

## <a name="example"></a>例

次の例は `search_for_value` 関数で、提供された `tree` オブジェクト内で値を検索します。 この関数に渡します、`for_all`メソッドでは、処理関数を指定された値を含むツリー ノードを見つけたときにスローします。

ある、`tree`クラスがサード パーティのライブラリによって提供されること、および変更することはできません。 ここでは、例外処理の使用は適切なので、`for_all`メソッドは提供しません、`task_group`または`structured_task_group`呼び出し元にオブジェクト。 したがって、処理関数では、直接は親タスク グループをキャンセルすることはできません。

タスク グループに提供する処理関数は、例外をスローするときに、ランタイムが (任意の子タスク グループを含む) タスク グループ内にあるすべてのタスクを停止し、まだ開始されていないすべてのタスクを破棄します。 `search_for_value`関数は、 `try` - `catch`ブロック、例外をキャプチャし、コンソールに結果を出力します。

[!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]

## <a name="example"></a>例

次の例では、作成、`tree`オブジェクトを並列でいくつかの値を探します。 `build_tree`関数がこのトピックの後半に示すようにします。

[!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]

この例では、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムを並列で値を検索します。 このアルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。

## <a name="example"></a>例

次の完全な例では、例外処理を使用して、基本的なツリー構造で値を検索します。

[!code-cpp[concrt-task-tree-search#5](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_5.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Found a node with value 32614.
Found a node with value 86131.
Did not find node with value 17522.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`task-tree-search.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc タスク-ツリー-search.cpp**

## <a name="see-also"></a>関連項目

[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)<br/>
[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[task_group クラス](reference/task-group-class.md)<br/>
[structured_task_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)<br/>
[parallel_for_each 関数](reference/concurrency-namespace-functions.md#parallel_for_each)

