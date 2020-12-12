---
description: '詳細については、「方法: キャンセルを使用して並列ループを中断する」を参照してください。'
title: '方法: キャンセル処理を使用して並列ループを中断する'
ms.date: 11/04/2016
helpviewer_keywords:
- writing a parallel search algorithm [Concurrency Runtime]
- parallel search algorithm, writing [Concurrency Runtime]
ms.assetid: 421cd2de-f058-465f-b890-dd8fcc0df273
ms.openlocfilehash: 0d2817e3a2645cb01d652b7858176ffce6df73c4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172519"
---
# <a name="how-to-use-cancellation-to-break-from-a-parallel-loop"></a>方法: キャンセル処理を使用して並列ループを中断する

この例では、キャンセルを使用して基本的な並列検索アルゴリズムを実装する方法を示します。

## <a name="example"></a>例

次の例では、キャンセルを使用して、配列内の要素を検索します。 関数は、 `parallel_find_any` [concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for) アルゴリズムと [concurrency:: run_with_cancellation_token](reference/concurrency-namespace-functions.md#run_with_cancellation_token) 関数を使用して、指定された値を含む位置を検索します。 並列ループは、値を検出すると、 [concurrency:: cancellation_token_source:: cancel](reference/cancellation-token-source-class.md#cancel) メソッドを呼び出して、将来の作業をキャンセルします。

[!code-cpp[concrt-parallel-array-search#1](../../parallel/concrt/codesnippet/cpp/how-to-use-cancellation-to-break-from-a-parallel-loop_1.cpp)]

[Concurrency::p arallel_for](reference/concurrency-namespace-functions.md#parallel_for)アルゴリズムは同時に動作します。 そのため、事前に決められた順序で操作は実行されません。 配列に値の複数のインスタンスが含まれている場合、結果はその位置のいずれかになります。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `parallel-array-search.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

> **cl.exe/EHsc parallel-array-search**

## <a name="see-also"></a>関連項目

[PPL における取り消し処理](cancellation-in-the-ppl.md)<br/>
[並列アルゴリズム](../../parallel/concrt/parallel-algorithms.md)<br/>
[parallel_for 関数](reference/concurrency-namespace-functions.md#parallel_for)<br/>
[cancellation_token_source クラス](../../parallel/concrt/reference/cancellation-token-source-class.md)
