---
title: '方法: マップを実行し、縮小操作を並列 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cda761da013e966f91848fed01a4f96f5d373021
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>方法: マップ操作と縮小操作を並列実行する

この例を使用する方法を示しています、 [concurrency::parallel_transform](reference/concurrency-namespace-functions.md#parallel_transform)と[concurrency::parallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce)アルゴリズムと[concurrency::concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md)ファイル内の単語の出現回数をカウントするクラス。  
  
 A*マップ*操作は、シーケンス内の各値に関数を適用します。 A*削減*操作が 1 つの値をシーケンスの要素を連結します。 C++ 標準ライブラリを使用する[std::transform](../../standard-library/algorithm-functions.md#transform)と[std::accumulate](../../standard-library/numeric-functions.md#accumulate)マップを実行し、操作を減らすために機能します。 ただし、多くの問題のパフォーマンスを向上させるために、`parallel_transform` アルゴリズムを使用して map 操作を並列実行し、`parallel_reduce` アルゴリズムを使用して reduce 操作を並列実行することができます。 場合によっては、`concurrent_unordered_map` を使用して、1 つの操作で map と reduce を実行できます。  
  
## <a name="example"></a>例  
 次の例では、ファイル内の単語の出現回数をカウントします。 使用して[std::vector](../../standard-library/vector-class.md)を 2 つのファイルの内容を表します。 map 操作は、各ベクター内の各単語の出現回数を計算します。 reduce 操作は、両方のベクターのワード カウントを累積します。  
  
 [!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コードをコンパイルするコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付ける`parallel-map-reduce.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列-マップ-reduce.cpp**  
  
## <a name="robust-programming"></a>信頼性の高いプログラミング  
 この例では、concurrent_unordered_map.h で定義されている `concurrent_unordered_map` クラスを使用して、1 つの操作で map と reduce を実行できます。  
  
 [!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]  
  
 通常、外側または内側のループのみ並列化します。 比較的ファイル数が少なく、各ファイルに含まれる単語が多い場合は、内側のループを並列化します。 比較的ファイル数が多く、各ファイルに含まれる単語が少ない場合は、外側のループを並列化します。  
  
## <a name="see-also"></a>関連項目  
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [parallel_transform 関数](reference/concurrency-namespace-functions.md#parallel_transform)   
 [parallel_reduce 関数](reference/concurrency-namespace-functions.md#parallel_reduce)   
 [concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
