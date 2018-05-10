---
title: '方法: 並列コンテナーを使用して効率を高める. |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- increasing efficiency with parallel containers [Concurrency Runtime]
- concurrent_queue class, examples
- concurrent_vector class, examples
ms.assetid: bd00046d-e9b6-4ae1-b661-3995f671b867
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f0e0d79693bef358a582e878ec2d6d138387752c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-parallel-containers-to-increase-efficiency"></a>方法: 並列コンテナーを使用して効率を向上させる
ここでは、並列コンテナーを使用して、データの格納とアクセスを並行して効率的に行う方法について説明します。  
  
 コード例では、素数とカーマイケル数のセットを並行して計算します。 次に、カーマイケル数ごとに、その数の素因数を計算します。  
  
## <a name="example"></a>例  
 次の例は、入力値が素数かどうかを調べる `is_prime` 関数と、入力値がカーマイケル数かどうかを調べる `is_carmichael` 関数を示しています。  
  
 [!code-cpp[concrt-carmichael-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_1.cpp)]  
  
## <a name="example"></a>例  
 次の例では、`is_prime` 関数と `is_carmichael` 関数を使用して、素数とカーマイケル数のセットを計算します。 この例では、 [concurrency::parallel_invoke](reference/concurrency-namespace-functions.md#parallel_invoke)と[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)それぞれを計算するアルゴリズムを並列で設定します。 並列アルゴリズムの詳細については、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
 この例では、 [concurrency::concurrent_queue](../../parallel/concrt/reference/concurrent-queue-class.md)カーマイケルのセットを保持するオブジェクトを作業キューとに後でそのオブジェクトを使用してそのための番号します。 使用して、 [::concurrent_vector](../../parallel/concrt/reference/concurrent-vector-class.md)素因数を検索する設定を後で反復処理をするために含まれる素数のセットを保持するオブジェクト。  
  
 [!code-cpp[concrt-carmichael-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_2.cpp)]  
  
## <a name="example"></a>例  
 次の例は、`prime_factors_of` 関数を示しています。この関数は試行除算を使用して、指定された値のすべての素因数を検出します。  
  
 この関数を使用して、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)素数のコレクションを反復処理するアルゴリズム。 `concurrent_vector` オブジェクトを使用すると、並行ループで素因数を結果に同時に加算できます。  
  
 [!code-cpp[concrt-carmichael-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-parallel-containers-to-increase-efficiency_3.cpp)]  
  
## <a name="example"></a>例  
 この例では、カーマイケル数のキュー内の各要素を、`prime_factors_of` 関数を呼び出してその素因数を計算することで処理します。 この作業を並列実行するために、タスク グループを使用します。 タスク グループの詳細については、次を参照してください。[タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
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
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`carmichael-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc carmichael-primes.cpp**  
  
## <a name="see-also"></a>関連項目  
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [タスクの並列化](../../parallel/concrt/task-parallelism-concurrency-runtime.md)   
 [concurrent_vector クラス](../../parallel/concrt/reference/concurrent-vector-class.md)   
 [concurrent_queue クラス](../../parallel/concrt/reference/concurrent-queue-class.md)   
 [parallel_invoke 関数](reference/concurrency-namespace-functions.md#parallel_invoke)   
 [parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)   
 [task_group クラス](reference/task-group-class.md)
