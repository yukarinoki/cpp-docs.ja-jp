---
title: '方法: combinable セットの結合を使用して |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 689dacb98bc9f8053686a02414151b4982edca67
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33695773"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>方法: combinable を使用して集合を結合する
このトピックの内容を使用する方法を示しています、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)クラスに含まれる素数の集合を計算します。  
  
## <a name="example"></a>例  
 次の例では、素数の集合を 2 回計算します。 それぞれの計算の結果を格納する、 [std::bitset](../../standard-library/bitset-class.md)オブジェクト。 この例ではまず、集合を逐次的に計算した後で、並列処理によっても計算します。 また、それぞれの計算に要する時間もコンソールに出力します。  
  
 この例では、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムと`combinable`スレッド ローカルのセットを生成するオブジェクト。 次を使用して、 [:combine_each](reference/combinable-class.md#combine_each)最終的なセットに、スレッド ローカルな集合を結合する方法です。  

  
 [!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]  
  
 4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。  
  
```Output  
serial time: 312 ms  
 
parallel time: 78 ms  
```  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`parallel-combine-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc 並列-結合-primes.cpp**  
  
## <a name="see-also"></a>関連項目  
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)   
 [combinable クラス](../../parallel/concrt/reference/combinable-class.md)   
 [combinable::combine_each メソッド](reference/combinable-class.md#combine_each)


