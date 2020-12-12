---
description: '詳細については、「方法: 組み合わせを使用してセットを結合する」を参照してください。'
title: '方法: combinable を使用して集合を結合する'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: da51bf8a2e7dd21432b9dcce73c6ead83ce23e35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172467"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>方法: combinable を使用して集合を結合する

このトピックでは、 [concurrency:: 組み合わせ](../../parallel/concrt/reference/combinable-class.md) 可能クラスを使用して素数のセットを計算する方法について説明します。

## <a name="example"></a>例

次の例では、素数の集合を 2 回計算します。 各計算では、結果が [std:: bitset](../../standard-library/bitset-class.md) オブジェクトに格納されます。 この例ではまず、集合を逐次的に計算した後で、並列処理によっても計算します。 また、それぞれの計算に要する時間もコンソールに出力します。

この例では、 [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムとオブジェクトを使用して、 `combinable` スレッドローカルセットを生成します。 次に、 [concurrency:: 組み合わせ可能:: combine_each](reference/combinable-class.md#combine_each) メソッドを使用して、スレッドローカルセットを最終セットに結合します。

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `parallel-combine-primes.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc parallel-combine-primes**

## <a name="see-also"></a>関連項目

[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[組み合わせ可能クラス](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable::combine_each メソッド](reference/combinable-class.md#combine_each)
