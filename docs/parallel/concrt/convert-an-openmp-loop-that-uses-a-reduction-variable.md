---
description: '詳細については、「方法: リダクション変数を使用する OpenMP ループを変換して同時実行ランタイムを使用する」を参照してください。'
title: '方法: 減少変数を使用する OpenMP ループを変換し、コンカレンシー ランタイムを使用する'
ms.date: 11/04/2016
helpviewer_keywords:
- converting from OpenMP to the Concurrency Runtime, reduction variables
- reduction variables, converting from OpenMP to the Concurrency Runtime
ms.assetid: 96623f36-5e57-4d3f-8c13-669e6cd535b1
ms.openlocfilehash: 131585caf3e06a11ed45bda4b58efa541272006f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325759"
---
# <a name="how-to-convert-an-openmp-loop-that-uses-a-reduction-variable-to-use-the-concurrency-runtime"></a>方法: 減少変数を使用する OpenMP ループを変換し、コンカレンシー ランタイムを使用する

この例では、[リダクション](../openmp/reference/openmp-clauses.md#reduction)句を使用する OpenMP [parallel](../../parallel/concrt/how-to-use-parallel-invoke-to-write-a-parallel-sort-routine.md#parallel)[for](../openmp/reference/openmp-directives.md#for-openmp)ループを変換して、同時実行ランタイムを使用する方法を示します。

OpenMP `reduction` 句を使用すると、並列領域の最後にあるリダクション演算の対象となる 1 つ以上のスレッド プライベート変数を指定できます。 OpenMP には、リダクション演算子のセットがあらかじめ定義されています。 各リダクション変数は、スカラーである必要があります (たとえば、、、など **`int`** **`long`** **`float`** )。 OpenMP には、並列領域でのリダクション変数の使用方法に関する制限事項もいくつか定義されています。

並列パターンライブラリ (PPL) は、 [concurrency:: の組み合わせ](../../parallel/concrt/reference/combinable-class.md) 可能なクラスを提供します。これにより、きめ細かな計算を実行し、その計算を最終結果にマージできます。 `combinable` クラスは、スカラー型と複合型の両方に作用するテンプレートです。 クラスを使用するには `combinable` 、parallel コンストラクトの本体でサブ計算を実行し、 [concurrency::](reference/combinable-class.md#combine) 組み合わせ可能:: 組み合わせまたは [concurrency:: 組み合わせ可能:: combine_each](reference/combinable-class.md#combine_each) メソッドを呼び出して最終的な結果を生成します。 `combine`メソッドと `combine_each` メソッドはそれぞれ、要素の各ペアを結合する方法を指定する *結合関数* を受け取ります。 したがって、`combinable` クラスは、リダクション演算子の固定セットだけに制限されません。

## <a name="example"></a>例

この例では、OpenMP とコンカレンシー ランタイムの両方を使用して、最初の 35 個のフィボナッチ数の合計を計算します。

[!code-cpp[concrt-openmp#7](../../parallel/concrt/codesnippet/cpp/convert-an-openmp-loop-that-uses-a-reduction-variable_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
Using OpenMP...
The sum of the first 35 Fibonacci numbers is 14930351.
Using the Concurrency Runtime...
The sum of the first 35 Fibonacci numbers is 14930351.
```

クラスの詳細については `combinable` 、「 [並列コンテナーとオブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)」を参照してください。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `concrt-omp-fibonacci-reduction.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc/openmp concrt-omp-fibonacci-reduction**

## <a name="see-also"></a>関連項目

[OpenMP からコンカレンシー ランタイムへの移行](../../parallel/concrt/migrating-from-openmp-to-the-concurrency-runtime.md)<br/>
[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)
