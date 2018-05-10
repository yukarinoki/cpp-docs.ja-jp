---
title: '方法: OpenMP の parallel for ループが同時実行ランタイムを使用する変換 |Microsoft ドキュメント'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 93538e3188f0086039ecc0b681f936954d82ae97
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>方法: OpenMP の parallel for ループを変換し、同時実行ランタイムを使用する

この例は、OpenMP を使用する基本的なループを変換する方法を示します[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)と[の](../../parallel/openmp/reference/for-openmp.md)同時実行ランタイムを使用するディレクティブ[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムです。  
  
## <a name="example"></a>例  
 この例では、OpenMP と同時実行ランタイムの両方を使用して、ランダム値の配列に含まれる素数の数を計算します。  
  
 [!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]  
  
 この例を実行すると、次の出力が生成されます。  
  
```Output  
Using OpenMP...  
found 107254 prime numbers.  
Using the Concurrency Runtime...  
found 107254 prime numbers.  
```  
  
 `parallel_for` アルゴリズムおよび OpenMP 3.0 では、インデックス型を符号付き整数型として使用することも、符号なし整数型として使用することもできます。 また、`parallel_for` アルゴリズムを使用すると、指定の範囲が符号付きの型をオーバーフローすることがなくなります。 OpenMP Version 2.0 および 2.5 では、符号付き整数のインデックス型しか使用できません。 また、OpenMP でインデックス範囲は検証されません。  
  
 この例では同時実行ランタイムのバージョンを使用しても、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)オブジェクトの代わりに、[アトミック](../../parallel/openmp/reference/atomic.md)を必要とせず、カウンターの値をインクリメントするディレクティブ同期。  
  
 詳細については`parallel_for`およびその他の並列アルゴリズムは、「[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)です。 詳細については、`combinable`クラスを参照してください[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)です。  
  
## <a name="example"></a>例  

 この例で動作する 1 つ前の変更、 [std::array](../../standard-library/array-class-stl.md)オブジェクトの代わりに、ネイティブ配列に対してです。 OpenMP version 2.0 および 2.5 の整数のインデックス型を符号付きでのみを許可するため、`parallel_for`構築、並列の C++ 標準ライブラリのコンテナーの要素にアクセスする反復子を使用することはできません。 並列パターン ライブラリ (PPL) は、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムで、タスク、コンテナー、反復コンテナーなど、C++ 標準ライブラリで提供されるもので、並列に実行します。 このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。 `parallel_for_each`アルゴリズムが、C++ 標準ライブラリに似ています[std::for_each](../../standard-library/algorithm-functions.md#for_each)点を除いて、アルゴリズム、`parallel_for_each`アルゴリズムは、タスクを同時に実行します。  
  
 [!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]  
  
## <a name="compiling-the-code"></a>コードのコンパイル  
 コード例をコピーし、Visual Studio プロジェクトに貼り付けるかという名前のファイルに貼り付けます`concrt-omp-count-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。  
  
 **cl.exe/EHsc/openmp concrt-omp-数-primes.cpp**  
  
## <a name="see-also"></a>関連項目  
 [OpenMP から同時実行ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)   
 [並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)   
 [並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)

