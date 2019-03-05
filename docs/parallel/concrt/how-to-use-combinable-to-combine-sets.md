---
title: '方法: 集合を結合する combinable を使用して'
ms.date: 11/04/2016
helpviewer_keywords:
- combinable class, example
- combining sets with combinable [Concurrency Runtime]
ms.assetid: 66ffe8e3-6bbb-4e9f-b790-b612922a68a7
ms.openlocfilehash: bf8a5bee65ea0ba1718c1d4d436b6af3e0b95961
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296099"
---
# <a name="how-to-use-combinable-to-combine-sets"></a>方法: 集合を結合する combinable を使用して

このトピックでは、使用する方法を示します、 [concurrency::combinable](../../parallel/concrt/reference/combinable-class.md)素数の集合を計算するクラス。

## <a name="example"></a>例

次の例では、素数の集合を 2 回計算します。 それぞれの計算に結果を格納する、 [std::bitset](../../standard-library/bitset-class.md)オブジェクト。 この例ではまず、集合を逐次的に計算した後で、並列処理によっても計算します。 また、それぞれの計算に要する時間もコンソールに出力します。

この例では、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムと`combinable`スレッド ローカルな集合を生成するオブジェクト。 次を使用して、 [:combine_each](reference/combinable-class.md#combine_each)最終的なセットにスレッド ローカルのセットを結合する方法。

[!code-cpp[concrt-parallel-combine-primes#1](../../parallel/concrt/codesnippet/cpp/how-to-use-combinable-to-combine-sets_1.cpp)]

4 つのプロセッサを備えたコンピューターを使用したときのサンプル出力を次に示します。

```Output
serial time: 312 ms

parallel time: 78 ms
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`parallel-combine-primes.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe /EHsc parallel-combine-primes.cpp**

## <a name="see-also"></a>関連項目

[並列コンテナーと並列オブジェクト](../../parallel/concrt/parallel-containers-and-objects.md)<br/>
[combinable クラス](../../parallel/concrt/reference/combinable-class.md)<br/>
[combinable::combine_each メソッド](reference/combinable-class.md#combine_each)
