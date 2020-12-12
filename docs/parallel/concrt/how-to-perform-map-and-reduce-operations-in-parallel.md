---
description: '詳細については、「方法: マップ操作と縮小操作を並列実行する」を参照してください。'
title: '方法: マップ操作と縮小操作を並列実行する'
ms.date: 11/04/2016
helpviewer_keywords:
- parallel_transform function, example
- parallel map and reduce, example
- parallel_reduce function, example
ms.assetid: 9d19fac0-4ab6-4380-a375-3b18eeb87720
ms.openlocfilehash: f35c9bf4df5a79cf9568bc286ff628e2f9fd45c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209842"
---
# <a name="how-to-perform-map-and-reduce-operations-in-parallel"></a>方法: マップ操作と縮小操作を並列実行する

この例では、 [concurrency::p arallel_transform](reference/concurrency-namespace-functions.md#parallel_transform) と concurrency: [:p arallel_reduce](reference/concurrency-namespace-functions.md#parallel_reduce) アルゴリズムおよび [concurrency:: concurrent_unordered_map](../../parallel/concrt/reference/concurrent-unordered-map-class.md) クラスを使用して、ファイル内の単語の出現回数をカウントする方法を示します。

*マップ* 操作は、シーケンスの各値に関数を適用します。 *Reduce* 操作は、シーケンスの要素を1つの値に結合します。 C++ 標準ライブラリの [std:: transform](../../standard-library/algorithm-functions.md#transform) 関数と [std:: 蓄積](../../standard-library/numeric-functions.md#accumulate) 関数を使用すると、map 操作と reduce 操作を実行できます。 ただし、多くの問題のパフォーマンスを向上させるために、`parallel_transform` アルゴリズムを使用して map 操作を並列実行し、`parallel_reduce` アルゴリズムを使用して reduce 操作を並列実行することができます。 場合によっては、`concurrent_unordered_map` を使用して、1 つの操作で map と reduce を実行できます。

## <a name="example"></a>例

次の例では、ファイル内の単語の出現回数をカウントします。 [Std:: vector](../../standard-library/vector-class.md)を使用して、2つのファイルの内容を表します。 map 操作は、各ベクター内の各単語の出現回数を計算します。 reduce 操作は、両方のベクターのワード カウントを累積します。

[!code-cpp[concrt-parallel-map-reduce#1](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_1.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コードをコンパイルするには、コードをコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `parallel-map-reduce.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc parallel-map-reduce**

## <a name="robust-programming"></a>信頼性の高いプログラミング

この例では、concurrent_unordered_map.h で定義されている `concurrent_unordered_map` クラスを使用して、1 つの操作で map と reduce を実行できます。

[!code-cpp[concrt-parallel-map-reduce#2](../../parallel/concrt/codesnippet/cpp/how-to-perform-map-and-reduce-operations-in-parallel_2.cpp)]

通常、外側または内側のループのみ並列化します。 比較的ファイル数が少なく、各ファイルに含まれる単語が多い場合は、内側のループを並列化します。 比較的ファイル数が多く、各ファイルに含まれる単語が少ない場合は、外側のループを並列化します。

## <a name="see-also"></a>関連項目

[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_transform 関数](reference/concurrency-namespace-functions.md#parallel_transform)<br/>
[parallel_reduce 関数](reference/concurrency-namespace-functions.md#parallel_reduce)<br/>
[concurrent_unordered_map クラス](../../parallel/concrt/reference/concurrent-unordered-map-class.md)
