---
title: '方法: 変換、OpenMP 並列 for ループ、同時実行ランタイムを使用するには'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, parallel for loops
- converting from OpenMP to the Concurrency Runtime, parallel loops
- parallel for loops, converting from OpenMP to the Concurrency Runtime
- parallel loops, converting from OpenMP to the Concurrency Runtime
ms.assetid: d8a7b656-f86c-456e-9c5d-a7d52f94646e
ms.openlocfilehash: bc408465f34f0558e9f426ae35b83d4610898414
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296138"
---
# <a name="how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime"></a>方法: 変換、OpenMP 並列 for ループ、同時実行ランタイムを使用するには

この例は、OpenMP を使用する基本的なループを変換する方法を示します[並列](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)と[の](../../parallel/openmp/reference/for-openmp.md)同時実行ランタイムを使用するディレクティブ[concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズム。

## <a name="example"></a>例

この例では、OpenMP とコンカレンシー ランタイムの両方を使用して、ランダム値の配列に含まれる素数の数を計算します。

[!code-cpp[concrt-openmp#1](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
Using OpenMP...
found 107254 prime numbers.
Using the Concurrency Runtime...
found 107254 prime numbers.
```


  `parallel_for` アルゴリズムおよび OpenMP 3.0 では、インデックス型を符号付き整数型として使用することも、符号なし整数型として使用することもできます。 また、`parallel_for` アルゴリズムを使用すると、指定の範囲が符号付きの型をオーバーフローすることがなくなります。 OpenMP Version 2.0 および 2.5 では、符号付き整数のインデックス型しか使用できません。 また、OpenMP でインデックス範囲は検証されません。

同時実行ランタイムを使用するこの例のバージョンを使用しても、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)オブジェクトの代わりに、[アトミック](../../parallel/openmp/reference/atomic.md)を必要とせず、カウンターの値をインクリメントするディレクティブ同期します。

詳細については`parallel_for`およびその他の並列アルゴリズムは、「[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)します。 詳細については、`combinable`クラスを参照してください[並列コンテナーとオブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)します。

## <a name="example"></a>例

この例で機能する 1 つ前の変更、 [std::array](../../standard-library/array-class-stl.md)オブジェクトの代わりに、ネイティブの配列にします。 OpenMP version 2.0 および 2.5 の整数のインデックス型を符号付きでのみを許可するため、`parallel_for`コンストラクト、並列での C++ 標準ライブラリ コンテナーの要素にアクセスする反復子を使用することはできません。 並列パターン ライブラリ (PPL) の提供、 [concurrency::parallel_for_each](reference/concurrency-namespace-functions.md#parallel_for_each)アルゴリズムで、C++ 標準ライブラリで提供されるものなど、反復的なコンテナーに同時に、タスクを実行します。 このアルゴリズムでは、`parallel_for` アルゴリズムで使用されるのと同じ分割ロジックが使用されます。 `parallel_for_each`アルゴリズムが、C++ 標準ライブラリに似ています[std::for_each](../../standard-library/algorithm-functions.md#for_each)点を除いて、アルゴリズム、`parallel_for_each`アルゴリズムでは、タスクを同時に実行します。

[!code-cpp[concrt-openmp#10](../../parallel/concrt/codesnippet/cpp/how-to-convert-an-openmp-parallel-for-loop-to-use-the-concurrency-runtime_2.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`concrt-omp-count-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe /EHsc /openmp concrt-omp-count-primes.cpp**

## <a name="see-also"></a>関連項目

[OpenMP からコンカレンシー ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)
