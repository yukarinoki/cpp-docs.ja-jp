---
title: '方法: キャンセル処理を使用して並列ループを中断する'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 2a19c2874ce331be2d4f5840f61cabf7bca9abf6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50612746"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>方法: キャンセル処理を使用して並列ループを中断する

この例では、キャンセルを使用して基本的な並列検索アルゴリズムを実装する方法を示します。

## <a name="example"></a>例

次の例では、キャンセルを使用して、配列内の要素を検索します。 `parallel_find_any`関数は、 [concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムと[concurrency::run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token)指定された値を含む位置を検索する関数。 並列ループには、値が検出されると、呼び出し、 [concurrency::cancellation_token_source::cancel](reference/cancellation-token-source-class.md#cancel)今後の作業をキャンセルするメソッド。

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Concurrency::parallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムが同時に動作します。 そのため、事前に決められた順序で操作を行うことはできません。 配列に値の複数のインスタンスが含まれている場合、結果の位置のいずれかを使用できます。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`parallel-array-search.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc 並列-配列-search.cpp**

## <a name="see-also"></a>関連項目

[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)
