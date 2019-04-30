---
title: '方法: 並列コンテナーを使用して、効率を向上させる'
ms.date: 11/04/2016
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
ms.openlocfilehash: 2479915b167ee3dbc2ce43d9c2733efc74818bbe
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62394443"
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>方法: 並列コンテナーを使用して、効率を向上させる

ここでは、並列コンテナーを使用して、データの格納とアクセスを並行して効率的に行う方法について説明します。

コード例では、素数とカーマイケル数のセットを並行して計算します。 次に、カーマイケル数ごとに、その数の素因数を計算します。

## <a name="example"></a>例

次の例は、入力値が素数かどうかを調べる `is_prime` 関数と、入力値がカーマイケル数かどうかを調べる `is_carmichael` 関数を示しています。

[!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]

## <a name="example"></a>例

次の例では、`is_prime` 関数と `is_carmichael` 関数を使用して、素数とカーマイケル数のセットを計算します。 この例では、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)と[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)それぞれ計算するアルゴリズムを並列で設定します。 並列アルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。

この例では、 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)は作業キューとしてに後でそのオブジェクトを使用してそのため、カーマイケルのセットを保持するオブジェクトの数値します。 使用して、 [concurrency::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)この素因数を検出するセットを反復処理には後であるために、素数のセットを保持するオブジェクト。

[!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]

## <a name="example"></a>例

次の例は、`prime_factors_of` 関数を示しています。この関数は試行除算を使用して、指定された値のすべての素因数を検出します。

この関数を使用して、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)素数のコレクションを反復処理するアルゴリズム。 `concurrent_vector` オブジェクトを使用すると、並行ループで素因数を結果に同時に加算できます。

[!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]

## <a name="example"></a>例

この例では、カーマイケル数のキュー内の各要素を、`prime_factors_of` 関数を呼び出してその素因数を計算することで処理します。 この作業を並列実行するために、タスク グループを使用します。 タスク グループの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)します。

この例では、カーマイケル数に 5 つ以上の素因数がある場合、カーマイケル数ごとに素因数を出力します。

[!code-cpp[concrt-carmichael-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_4.cpp)]

## <a name="example"></a>例

並列コンテナーを使用してカーマイケル数の素因数を計算する、完全なコード例を次に示します。

[!code-cpp[concrt-carmichael-primes#5](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_5.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Prime factors of 9890881 are: 7 11 13 41 241.
Prime factors of 825265 are: 5 7 17 19 73.
Prime factors of 1050985 are: 5 13 19 23 37.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`carmichael-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe /EHsc carmichael-primes.cpp**

## <a name="see-also"></a>関連項目

[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)<br/>
[concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)<br/>
[concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)<br/>
[parallel_invoke 関数](reference/concurrency-namespace-functions.md#parallel_invoke)<br/>
[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[task_group クラス](reference/task-group-class.md)
