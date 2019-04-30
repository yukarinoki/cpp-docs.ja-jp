---
title: '方法: Parallel.invoke to Execute Parallel Operations を使用してください。'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_invoke function, example
- calling multiple functions in parallel [Concurrency Runtime]
ms.assetid: a6aea69b-d647-4b7e-bf3b-e6a6a9880072
ms.openlocfilehash: d618b5f202c6aaf454a60f4f37211d9000600562
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62345657"
---
# <a name="how-to-use-parallelinvoke-to-execute-parallel-operations"></a>方法: Parallel.invoke to Execute Parallel Operations を使用してください。

この例は、使用する方法を示します、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)共有データ ソースに対して複数の操作を実行するプログラムのパフォーマンスを向上させるアルゴリズム。 操作によってソースが変更されるわけではないため、簡単に並列実行できます。

## <a name="example"></a>例

次のコード例について考えます。このコードは、`MyDataType` 型の変数を作成し、関数を呼び出してその変数を初期化し、そのデータに対して時間のかかる複数の操作を実行します。

[!code-cpp[concrt-parallel-word-mining#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_1.cpp)]

`lengthy_operation1`、`lengthy_operation2`、および `lengthy_operation3` の各関数が `MyDataType` 変数を変更しない場合は、追加の修正を行わなくても、これらの関数を並列に実行できます。

## <a name="example"></a>例

次の例では、並列で実行するように前の例を修正します。 `parallel_invoke` アルゴリズムは、各タスクを並列に実行し、すべてのタスクが終了した後に制御を戻します。

[!code-cpp[concrt-parallel-word-mining#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_2.cpp)]

## <a name="example"></a>例

次の例ではダウンロード*The Iliad* gutenberg.org から Homer によると、そのファイルに対して複数の操作を実行します。 この例では、これらの操作を逐次的に実行してから、同じ操作を並列に実行します。

[!code-cpp[concrt-parallel-word-mining#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-invoke-to-execute-parallel-operations_3.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Downloading 'The Iliad'...

Running serial version... took 953 ms.
Running parallel version... took 656 ms.

The most common words that have five or more letters are:
    their (953)
    shall (444)
    which (431)
    great (398)
    Hector (349)
    Achilles (309)
    through (301)
    these (268)
    chief (259)
The longest sequence of words that have the same first letter is:
    through the tempest to the tented
The following palindromes appear in the text:
    spots stops
    speed deeps
    keels sleek
```

この例では、`parallel_invoke` アルゴリズムを使用して、同じデータ ソースに対して作用する複数の関数を呼び出します。 `parallel_invoke` アルゴリズムを使用すると、同じデータ ソースに対して作用する関数だけでなく、任意の関数セットを並列に呼び出すことができます。

`parallel_invoke` アルゴリズムでは各処理関数を並列で呼び出すため、そのパフォーマンスは (ランタイムが各関数を別々のプロセッサで処理する場合に) 最も時間がかかる関数によって制限されます。 この例で、使用できるプロセッサの数よりも多くのタスクを並列で実行すると、各プロセッサで複数のタスクを実行できます。 その場合のパフォーマンスは、最も時間のかかるタスクのグループによって制限されます。

この例では 3 つのタスクを並列に実行するので、4 つ以上のプロセッサを搭載したコンピューターではパフォーマンスの向上を期待できません。 パフォーマンスを向上させるには、最も時間のかかるタスクを小さなタスクに分割し、それらのタスクを並列に実行します。

使用することができます、`parallel_invoke`アルゴリズムの代わりに、 [concurrency::task_group](reference/task-group-class.md)と[concurrency::structured_task_group](../../parallel/concrt/reference/structured-task-group-class.md)クラスのキャンセルのサポートを必要としない場合。 使用量を比較する例については、`parallel_invoke`アルゴリズムとタスクのグループを参照してください[方法。Parallel_invoke を使用して並列並べ替えルーチンを記述する](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md)します。

## <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするにコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`parallel-word-mining.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc/MD/DUNICODE 用並列 word mining.cpp**

## <a name="see-also"></a>関連項目

[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_invoke 関数](reference/concurrency-namespace-functions.md#parallel_invoke)
