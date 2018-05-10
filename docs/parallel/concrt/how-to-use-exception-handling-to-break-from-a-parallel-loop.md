---
title: '方法: 並列ループから処理を中断する例外を使用して |Microsoft ドキュメント'
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
ms.openlocfilehash: 6bacb9ea6a451026f7a515878cb649090ed9cbf4
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-exception-handling-to-break-from-a-parallel-loop"></a>方法: 例外処理を使用して並列ループを中断する
このトピックでは、基本的なツリー構造の検索アルゴリズムを記述する方法を示します。  
  
 トピック[キャンセル](cancellation-in-the-ppl.md)並列パターン ライブラリでキャンセル処理の役割について説明します。 例外処理を使用するは、小さいを効率的に使用するよりも並列処理の取り消し、 [concurrency::task_group::cancel](reference/task-group-class.md#cancel)と[concurrency::structured_task_group::cancel](reference/structured-task-group-class.md#cancel)メソッドです。 ただし、ここでの処理を取り消す例外処理の使用は適切なシナリオの 1 つはタスクまたは並列アルゴリズムを使用していては提供されませんサード パーティ製ライブラリを呼び出すときに、`task_group`または`structured_task_group`をキャンセルするオブジェクト。  

  
## <a name="example"></a>例  
 次の例は、基本的な`tree`データ要素と子ノードのリストを含む型。 次のセクションの本文を表示する、`for_all`メソッド、再帰的には、それぞれの子ノードの作業の機能を実行します。  
  
 [!code-cpp[concrt-task-tree-search#2](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_1.cpp)]  
  
## <a name="example"></a>例  
 次の例は、`for_all`メソッドです。 使用して、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムを並列でツリーの各ノードで、処理関数を実行します。  
  
 [!code-cpp[concrt-task-tree-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_2.cpp)]  
  
## <a name="example"></a>例  
 次の例は `search_for_value` 関数で、提供された `tree` オブジェクト内で値を検索します。 この関数に渡します、`for_all`作業関数を指定された値を含むツリー ノードが検出した場合にスローするメソッド。  
  
 あると想定、`tree`クラスは、サードパーティのライブラリによって提供および変更することはできません。 ここでは、例外処理の使用は適切なので、`for_all`メソッドは提供しません、`task_group`または`structured_task_group`を呼び出し元のオブジェクト。 そのため、処理関数は直接親タスク グループを取り消すことはできません。  
  
 タスク グループに提供する処理関数は、例外をスローするときに、ランタイムは (子タスク グループを含む)、タスク グループ内にあるすべてのタスクを停止し、まだ開始されていないタスクを破棄します。 `search_for_value`関数は、 `try` - `catch`ブロックは例外をキャプチャし、コンソールに結果を出力します。  
  
 [!code-cpp[concrt-task-tree-search#3](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_3.cpp)]  
  
## <a name="example"></a>例  
 次の例を作成、`tree`オブジェクトを並列で複数の値を検索します。 `build_tree`関数がこのトピックの後半に示すようにします。  
  
 [!code-cpp[concrt-task-tree-search#4](../../parallel/concrt/codesnippet/cpp/how-to-use-exception-handling-to-break-from-a-parallel-loop_4.cpp)]  
  
 この例では、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)アルゴリズムを並列で値を検索します。 このアルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
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
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`task-tree-search.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc タスクのツリーの search.cpp**  
  
## <a name="see-also"></a>関連項目  
 [PPL における取り消し処理](cancellation-in-the-ppl.md)   
 [例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)   
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [task_group クラス](reference/task-group-class.md)   
 [structured_task_group クラス](../../parallel/concrt/reference/structured-task-group-class.md)   
 [parallel_for_each 関数](reference/concurrency-namespace-functions.md#parallel_for_each)


