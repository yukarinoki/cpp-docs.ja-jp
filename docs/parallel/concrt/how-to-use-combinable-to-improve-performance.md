---
title: '方法: パフォーマンスを向上させる combinable を使用して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- improving parallel performance with combinable [Concurrency Runtime]
ms.assetid: fa730580-1c94-4b2d-8aec-57c91dc0497e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3185ee9f7546e6927197d2e3452ea4cf86f9ab5c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-use-combinable-to-improve-performance"></a>方法: combinable を使用してパフォーマンスを向上させる
この例を使用する方法を示しています、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラス内の数値の合計を計算する、 [std::array](../../standard-library/array-class-stl.md)素数であるオブジェクト。 `combinable` クラスは、共有状態を解消することでパフォーマンスを向上します。  
  
> [!TIP]
>  場合によっては、並行してマップ ([concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)) を削減し、([concurrency:: parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)) 経由でのパフォーマンスの向上を実現できる`combinable`です。 例については、使用してマップ操作と縮小この例と同じ結果を生成するために、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
## <a name="example"></a>例  
 次の例では、 [std::accumulate](../../standard-library/numeric-functions.md#accumulate)素数である配列内の要素の合計を計算する関数。 この例では、`a` は `array` オブジェクトであり、入力値が素数であるかどうかを判定するために `is_prime` 関数を使用します。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_1.cpp)]  
  
## <a name="example"></a>例  

 次の例では、前の例の並列化を単純な方法で示します。 この例では、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)配列を並列で処理するためのアルゴリズムと[concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)オブジェクトへのアクセスを同期するために、`prime_sum`変数. この例では、共有リソースが使用できるようになるのを各スレッドが待機する必要があるため、効率は改善されません。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#2](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_2.cpp)]  
  
## <a name="example"></a>例  
 `combinable` オブジェクトを使用して、前の例のパフォーマンスを向上する例を次に示します。 この例では、同期オブジェクトが不要となっています。`combinable` オブジェクトを使用することにより、各スレッドがタスクを独立して実行できるため、効率が改善されます。  
  
 通常、`combinable` オブジェクトは次の手順で使用します。 最初に、処理を並列で実行して、詳細な計算結果を生成します。 次に、この計算結果を結合 (換算) して最終結果を生成します。 この例では、 [concurrency::combinable::local](reference/combinable-class.md#local)ローカルの合計への参照を取得します。 次を使用して、 [concurrency::combinable::combine](reference/combinable-class.md#combine)メソッドおよび[:plus](../../standard-library/plus-struct.md)最終結果に、ローカルの計算を結合するオブジェクト。  

  
 [!code-cpp[concrt-parallel-sum-of-primes#3](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_3.cpp)]  
  
## <a name="example"></a>例  
 次のコード例全体では、素数の合計を逐次処理と並列処理の両方で計算します。 この例では、両方の計算に要する時間もコンソールに出力します。  
  
 [!code-cpp[concrt-parallel-sum-of-primes#4](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-improve-performance_4.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
```Output  
1709600813  
serial time: 6178 ms  
 
1709600813  
parallel time: 1638 ms  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`parallel-sum-of-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列の合計-の-primes.cpp**  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 例については、使用してマップ操作と縮小、同じ結果を生成するために、次を参照してください。[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。  
  
## <a name="see-also"></a>関連項目  
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)   
 [critical_section クラス](../../parallel/concrt/reference/critical-section-class.md)
