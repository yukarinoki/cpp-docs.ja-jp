---
title: '方法: メッセージ ブロック フィルターを使用します。'
ms.date: 11/04/2016
helpviewer_keywords:
- message-block filters, using [Concurrency Runtime]
- using message-block filters [Concurrency Runtime]
ms.assetid: db6b99fb-288d-4477-96dc-b9751772ebb2
ms.openlocfilehash: 1bfa11953d27dc7e013e715b3f58111f124caeaf
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62321943"
---
# <a name="how-to-use-a-message-block-filter"></a>方法: メッセージ ブロック フィルターを使用します。

ここでは、フィルター関数を使用して、非同期メッセージ ブロックでメッセージの受け入れや拒否がメッセージ ペイロードに基づいて行われるようにする方法について説明します。

など、メッセージ ブロック オブジェクトを作成するときに、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)、 [concurrency::call](../../parallel/concrt/reference/call-class.md)、または[concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)、を指定することができます*filter 関数*メッセージ ブロックを受け入れるか、メッセージが拒否されたかどうかを決定します。 フィルター関数は、メッセージ ブロックが特定の値のみを受信するようにする便利な方法です。

フィルター関数は、メッセージ ブロックを接続することができるため、重要な*データフロー ネットワーク*します。 データ フロー ネットワークでは、メッセージ ブロックが特定の基準を満たすメッセージのみを処理することによってデータのフローを制御します。 このモデルと制御フロー モデルを比較してください。制御フロー モデルでは、条件付きステートメントやループなどの制御構造体を使用してデータのフローが調整されます。

ここでは、メッセージ フィルターの基本的な使用例を示します。 メッセージ フィルターとデータ フロー モデルを使用して、メッセージ ブロックを接続するその他の例では、次を参照してください。[チュートリアル。データフロー エージェントの作成](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)と[チュートリアル。イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)です。

## <a name="example"></a>例

次の関数 `count_primes` について考えます。この関数では、受信メッセージをフィルター処理しないメッセージ ブロックの基本的な使用方法を示します。 メッセージ ブロックは、素数を追加、 [std::vector](../../standard-library/vector-class.md)オブジェクト。 `count_primes` 関数は、いくつかの数をメッセージ ブロックに送信し、メッセージ ブロックから出力値を受信し、素数をコンソールに出力します。

[!code-cpp[concrt-primes-filter#1](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_1.cpp)]

`transformer` オブジェクトはすべての入力値を処理します。ただし、必要なのは素数のみです。 メッセージ送信側が素数のみを送信するようにアプリケーションを記述することもできますが、メッセージ受信側の要件が必ずしも判明しているとは限りません。

## <a name="example"></a>例

次の関数 `count_primes_filter` は、`count_primes` 関数と同じタスクを実行します。 ただし、このバージョンの `transformer` オブジェクトは、フィルター関数を使用して素数のみを受け入れます。 アクションを実行する関数は素数のみを受信するため、`is_prime` 関数を呼び出す必要はありません。

`transformer` オブジェクトは素数のみを受信するため、`transformer` オブジェクト自体にそれらの素数を保持できます。 つまり、この例の `transformer` オブジェクトは、素数を `vector` オブジェクトに追加する必要はありません。

[!code-cpp[concrt-primes-filter#2](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_2.cpp)]

今回の `transformer` オブジェクトは素数のみを処理します。 前の例の `transformer` オブジェクトはすべてのメッセージを処理します。 したがって、前の例では、送信メッセージの数と受信メッセージの数が一致する必要があります。 この例の結果を使用して、 [concurrency::send](reference/concurrency-namespace-functions.md#send)から受信するメッセージの数を決定する関数、`transformer`オブジェクト。 `send`関数が返される**true**メッセージ バッファーがメッセージを受け入れると**false**メッセージ バッファーがメッセージを拒否する場合。 したがって、メッセージ バッファーがメッセージを受け入れる回数は、素数の数と一致します。

## <a name="example"></a>例

コード例全体を次に示します。 この例では、`count_primes` 関数と `count_primes_filter` 関数の両方を呼び出します。

[!code-cpp[concrt-primes-filter#3](../../parallel/concrt/codesnippet/cpp/how-to-use-a-message-block-filter_3.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`primes-filter.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc primes-filter.cpp**

## <a name="robust-programming"></a>信頼性の高いプログラミング

ラムダ関数、関数ポインター、または関数オブジェクトをフィルター関数として使用できます。 各フィルター関数の形式は次のいずれかになります。

```Output
bool (T)
bool (T const &)
```

データの不必要なコピーをなくすには、値で伝達される集約型を扱うときに 2 番目の形式を使用します。

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[チュートリアル: データフロー エージェントの作成](../../parallel/concrt/walkthrough-creating-a-dataflow-agent.md)<br/>
[チュートリアル: イメージ処理ネットワークの作成](../../parallel/concrt/walkthrough-creating-an-image-processing-network.md)<br/>
[transformer クラス](../../parallel/concrt/reference/transformer-class.md)
