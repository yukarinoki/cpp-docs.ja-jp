---
description: '詳細については、「方法: 並列コンテナーを使用して効率を向上させる」を参照してください。'
title: '方法: 並列コンテナーを使用して効率を向上させる'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: 6e416da7b1cdcbe1a9b3073569cf4dda6434ceea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341556"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>方法: 並列コンテナーを使用して効率を向上させる

ここでは、並列コンテナーを使用して、データの格納とアクセスを並行して効率的に行う方法について説明します。

コード例では、素数とカーマイケル数のセットを並行して計算します。 次に、カーマイケル数ごとに、その数の素因数を計算します。

## <a name="example-determine-if-an-input-value-is-a-prime-number"></a>例: 入力値が素数であるかどうかを確認する

次の例は、入力値が素数かどうかを調べる `is_prime` 関数と、入力値がカーマイケル数かどうかを調べる `is_carmichael` 関数を示しています。

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example-compute-prime-and-carmichael-numbers"></a>例: 計算素数とカーマイケル数

次の例では、`is_prime` 関数と `is_carmichael` 関数を使用して、素数とカーマイケル数のセットを計算します。 この例では、 [concurrency::p arallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke) と [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムを使用して、各セットを並列に計算します。 並列アルゴリズムの詳細については、「 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)」を参照してください。

この例では、 [concurrency:: concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md) オブジェクトを使用して、カーマイケル数のセットを保持します。これは、後でそのオブジェクトを作業キューとして使用するためです。 この例では、 [concurrency:: concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md) オブジェクトを使用して素数のセットを保持しています。これは、後でこのセットを反復処理して素数を検出するためです。

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example-find-all-prime-factors-of-a-given-value"></a>例: 指定された値のすべての素要因を検索する

次の例は、`prime_factors_of` 関数を示しています。この関数は試行除算を使用して、指定された値のすべての素因数を検出します。

この関数は、 [concurrency::p arallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each) アルゴリズムを使用して、素数のコレクションを反復処理します。 `concurrent_vector` オブジェクトを使用すると、並行ループで素因数を結果に同時に加算できます。

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example-processes-each-element-in-the-queue-of-carmichael-numbers"></a>例: Carmichael 数のキュー内の各要素を処理する

この例では、カーマイケル数のキュー内の各要素を、`prime_factors_of` 関数を呼び出してその素因数を計算することで処理します。 この作業を並列実行するために、タスク グループを使用します。 タスクグループの詳細については、「 [タスクの並列](../../parallel/concrt/task-parallelism-concurrency-runtime.md)化」を参照してください。

この例では、カーマイケル数に 5 つ以上の素因数がある場合、カーマイケル数ごとに素因数を出力します。

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example-finished-parallel-container-code-sample"></a>例: 完成した並列コンテナーのコードサンプル

並列コンテナーを使用してカーマイケル数の素因数を計算する、完全なコード例を次に示します。

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `carmichael-primes.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc carmichael-primes**

## <a name="see-also"></a>関連項目

[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[タスクの並列処理](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[parallel_invoke 関数](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group クラス](reference/task-group-class.md)
