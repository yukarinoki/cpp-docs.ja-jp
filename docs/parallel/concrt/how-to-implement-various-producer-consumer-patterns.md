---
title: '方法: さまざまなプロデューサー/コンシューマー パターンを実装する'
ms.date: 11/04/2016
helpviewer_keywords:
- producer-consumer patterns, implementing [Concurrency Runtime]
- implementing producer-consumer patterns [Concurrency Runtime]
ms.assetid: 75f2c7cc-5399-49ea-98eb-847fe6747169
ms.openlocfilehash: 70813adf6715a2bcaf4af7370ce43d99c44263bd
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/28/2020
ms.locfileid: "91413776"
---
# <a name="how-to-implement-various-producer-consumer-patterns"></a>方法: さまざまなプロデューサー/コンシューマー パターンを実装する

ここでは、アプリケーションにプロデューサー/コンシューマー パターンを実装する方法について説明します。 このパターンでは、"*プロデューサー*" がメッセージをメッセージ ブロックに送信し、"*コンシューマー*" がそのブロックからメッセージを読み取ります。

このトピックでは、2 つのシナリオに従って説明します。 最初のシナリオでは、コンシューマーはプロデューサーが送信した各メッセージを受信する必要があります。 2 番目のシナリオでは、コンシューマーは定期的にデータをポーリングします。そのため、各メッセージを受信する必要はありません。

このトピックのどちらの例も、エージェント、メッセージ ブロック、およびメッセージ パッシング関数を使用して、メッセージをプロデューサーからコンシューマーに転送します。 プロデューサーエージェントは、concurrency [:: send](reference/concurrency-namespace-functions.md#send) 関数を使用して、 [Concurrency:: ITarget](../../parallel/concrt/reference/itarget-class.md) オブジェクトにメッセージを書き込みます。 コンシューマーエージェントは、concurrency: [: receive](reference/concurrency-namespace-functions.md#receive) 関数を使用して、 [Concurrency:: ISource](../../parallel/concrt/reference/isource-class.md) オブジェクトからメッセージを読み取ります。 どちらのエージェントにも、処理の終了を調整するための sentinel 値が保持されます。

非同期エージェントの詳細については、「 [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)」を参照してください。 メッセージブロックとメッセージパッシング関数の詳細については、「 [非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md) と [メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)」を参照してください。

## <a name="example-send-series-of-numbers-to-consumer-agent"></a>例: 一連の数値をコンシューマーエージェントに送信する

この例では、プロデューサー エージェントは一連の数字をコンシューマー エージェントに送信します。 コンシューマーはこれらの各数字を受け取り、その平均を計算します。 アプリケーションはその平均をコンソールに出力します。

この例では、 [concurrency:: unbounded_buffer](reference/unbounded-buffer-class.md) オブジェクトを使用して、プロデューサーがメッセージをキューにすることを有効にします。 `unbounded_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーと共有バッファーとの間でメッセージを送受信できるようにします。 `send` 関数および `receive` 関数で、プロデューサーからコンシューマーにデータを伝達するタスクを調整します。

[!code-cpp[concrt-producer-consumer-average#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_1.cpp)]

この例を実行すると、次の出力が生成されます。

```Output
The average is 50.
```

## <a name="example-send-series-of-stock-quotes-to-consumer-agent"></a>例: 一連の株価をコンシューマーエージェントに送信する

この例では、プロデューサー エージェントは一連の株式相場をコンシューマー エージェントに送信します。 コンシューマー エージェントは定期的に現在の相場を読み取り、それをコンソールに出力します。

この例は前の例と似ていますが、 [concurrency:: overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md) オブジェクトを使用してプロデューサーが1つのメッセージをコンシューマーと共有できるようにする点が異なります。 前の例と同様に、`overwrite_buffer` クラスに、`ITarget` および `ISource` を実装して、プロデューサーおよびコンシューマーが共有メッセージ バッファーを操作できるようにします。

[!code-cpp[concrt-producer-consumer-quotes#1](../../parallel/concrt/codesnippet/cpp/how-to-implement-various-producer-consumer-patterns_2.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Current quote is 24.44.
Current quote is 24.44.
Current quote is 24.65.
Current quote is 24.99.
Current quote is 23.76.
Current quote is 22.30.
Current quote is 25.89.
```

`unbounded_buffer` オブジェクトとは異なり、`receive` 関数によって、`overwrite_buffer` オブジェクトからメッセージが削除されることはありません。 プロデューサーがメッセージを上書きする前に、コンシューマーがメッセージ バッファーから 2 回以上読み取りを行った場合、コンシューマーは毎回同じメッセージを取得します。

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付けて `producer-consumer.cpp` から、Visual studio のコマンドプロンプトウィンドウで次のコマンドを実行します。

**cl.exe/EHsc producer-consumer**

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)<br/>
[非同期メッセージブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)
