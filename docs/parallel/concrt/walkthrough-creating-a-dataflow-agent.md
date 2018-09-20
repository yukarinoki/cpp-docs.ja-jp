---
title: 'チュートリアル: データフロー エージェントの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating dataflow agents [Concurrency Runtime]
- dataflow agents, creating [Concurrency Runtime]
ms.assetid: 9db5ce3f-c51b-4de1-b79b-9ac2a0cbd130
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c71bfa1eb9acb270195549eec950fb4fdf6c31b3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438952"
---
# <a name="walkthrough-creating-a-dataflow-agent"></a>チュートリアル: データフロー エージェントの作成

ここでは、制御フローではなくデータ フローに基づくエージェント ベースのアプリケーションを作成する方法について説明します。

*制御フロー*プログラムで操作の実行順序を指します。 制御フローは、条件付きステートメントやループなどの制御構造体を使用して調整されます。 または、*データフロー*を計算が行われるすべての必要なデータが使用可能な場合にのみ、プログラミング モデルを指します。 データ フロー プログラミング モデルは、プログラムの独立したコンポーネントどうしがメッセージを送信することによって通信する、メッセージ パッシングの概念に関連しています。

非同期エージェントでは、制御フロー モデルとデータ フロー プログラミング モデルの両方がサポートされています。 制御フロー モデルはほとんどの状況に適していますが、エージェントがデータを受信し、そのデータのペイロードに基づいてアクションを実行するなどの状況ではデータ フロー モデルの方が適しています。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [方法: メッセージ ブロック フィルターを使用する](../../parallel/concrt/how-to-use-a-message-block-filter.md)

##  <a name="top"></a> セクション

このチュートリアルは、次のセクションで構成されています。

- [基本的な制御フロー エージェントを作成します。](#control-flow)

- [基本的なデータフロー エージェントの作成](#dataflow)

- [メッセージ ログ エージェントを作成します。](#logging)

##  <a name="control-flow"></a> 基本的な制御フロー エージェントを作成します。

`control_flow_agent` クラスを定義する次の例について考えます。 `control_flow_agent` クラスは、1 つの入力バッファーと 2 つの出力バッファーの合計 3 つのメッセージ バッファーに対して作用します。 `run` メソッドは、ループ内でソース メッセージ バッファーから読み取り、条件付きステートメントを使用してプログラムの実行フローを調整します。 エージェントは、ゼロ以外の負の値に対してカウンターの 1 つをインクリメントし、ゼロ以外の正の値に対して別のカウンターをインクリメントします。 エージェントは、sentinel 値のゼロを受信すると、カウンターの値を出力メッセージ バッファーに送信します。 `negatives` メソッドと `positives` メソッドは、アプリケーションがエージェントから負の値と正の値のカウントを読み取ることができるようにします。

[!code-cpp[concrt-dataflow-agent#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_1.cpp)]

この例では、エージェントで制御フローを使用する基本的な方法しか示していませんが、制御フロー ベースのプログラミングの逐次的性質は明らかです。 入力メッセージ バッファーに複数のメッセージが存在していても、各メッセージは逐次的に処理される必要があります。 データ フロー モデルでは、条件付きステートメントの両方の分岐を同時に評価できます。 データ フロー モデルでは、データが使用可能になったときにそのデータに作用する複雑なメッセージング ネットワークを作成することもできます。

[[トップ](#top)]

##  <a name="dataflow"></a> 基本的なデータフロー エージェントの作成

ここでは、`control_flow_agent` クラスからデータ フロー モデルに切り替えて、同じタスクを実行する方法について説明します。

データ フロー エージェントを使用するには、メッセージ バッファーのネットワークを作成し、それぞれのメッセージ バッファーが特定の用途で機能するようにします。 一部のメッセージ ブロックでは、フィルター関数を使用して、メッセージの受け入れまたは拒否をメッセージ ペイロードに基づいて行います。 フィルター関数を使用すると、メッセージ ブロックが特定の値のみを受信するようになります。

#### <a name="to-convert-the-control-flow-agent-to-a-dataflow-agent"></a>制御フロー エージェントからデータ フロー エージェントに切り替えるには

1. `control_flow_agent` クラスの本体を別のクラス (`dataflow_agent` など) にコピーします。 代わりに、`control_flow_agent` クラスの名前を変更してもかまいません。

1. `receive` を呼び出すループの本体を `run` メソッドから削除します。

[!code-cpp[concrt-dataflow-agent#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_2.cpp)]

1. `run` メソッド内の `negative_count` および `positive_count` 変数の初期化コードの後に、アクティブな操作のカウントを追跡する `countdown_event` オブジェクトを追加します。

[!code-cpp[concrt-dataflow-agent#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_3.cpp)]

     The `countdown_event` class is shown later in this topic.

1. データ フロー ネットワークに参加するメッセージ バッファー オブジェクトを作成します。

[!code-cpp[concrt-dataflow-agent#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_4.cpp)]

1. メッセージ バッファーを接続してネットワークを形成します。

[!code-cpp[concrt-dataflow-agent#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_5.cpp)]

1. `event` オブジェクトと `countdown event` オブジェクトが設定されるまで待ちます。 これらのイベントは、エージェントが sentinel 値を受信したことと、すべての操作が完了したことを通知します。

[!code-cpp[concrt-dataflow-agent#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_6.cpp)]

次の図は、`dataflow_agent` クラスの完全なデータ フロー ネットワークを示しています。

![データ フロー ネットワーク](../../parallel/concrt/media/concrt_dataflow.png "concrt_dataflow")

ネットワークのメンバーを次の表に示します。

|メンバー|説明|
|------------|-----------------|
|`increment_active`|A [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)オブジェクトのアクティブなイベント カウンターをインクリメントし、ネットワークの残りの部分に、入力値を渡します。|
|`negatives`, `positives`|[concurrency::call](../../parallel/concrt/reference/call-class.md)アクティブなイベント カウンターの数値とデクリメントのカウントをインクリメントするオブジェクト。 各オブジェクトは、フィルターを使用して、負の数または正の数を受け入れます。|
|`sentinel`|A [concurrency::call](../../parallel/concrt/reference/call-class.md)をアクティブなイベント カウンターはゼロでデクリメント sentinel 値のみを受け入れるオブジェクト。|
|`connector`|A [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)ソース メッセージ バッファーを内部ネットワークに接続するオブジェクト。|

`run` メソッドは別個のスレッドで呼び出されるため、ネットワークが完全に接続される前に、他のスレッドからネットワークにメッセージが送信されることがあります。 `_source` データ メンバーは、アプリケーションからエージェントに送信されるすべての入力をバッファーに格納する `unbounded_buffer` オブジェクトです。 ネットワークですべての入力メッセージが処理されるように、エージェントは最初にネットワークの内部ノードをリンクしてから、そのネットワークの始端 `connector` を `_source` データ メンバーにリンクします。 これにより、ネットワークの形成中にメッセージが処理されることがなくなります。

この例のネットワークは制御フローではなくデータ フローに基づいているため、各入力値の処理が終了したこと、および sentinel ノードがその値を受信したことがエージェントに通知される必要があります。 この例では、`countdown_event`オブジェクトからすべての入力値が処理されたことを通知し、 [concurrency::event](../../parallel/concrt/reference/event-class.md) sentinel ノードがその値を受信したことを示すオブジェクト。 `countdown_event` クラスは、`event` オブジェクトを使用して、カウンター値がゼロになったときに通知します。 データ フロー ネットワークのヘッド ノードは、値を受信するたびにカウンターをインクリメントします。 ネットワークの各ターミナル ノードは、入力値を処理した後、カウンターをデクリメントします。 エージェントは、データ フロー ネットワークを形成した後、sentinel ノードが `event` オブジェクトを設定し、カウンターがゼロになったことが `countdown_event` オブジェクトから通知されるまで待機します。

次の例では、`control_flow_agent`、`dataflow_agent`、および `countdown_event` クラスを示します。 `wmain` 関数は、`control_flow_agent` オブジェクトと `dataflow_agent` オブジェクトを作成し、`send_values` 関数を使用して一連のランダム値をエージェントに送信します。

[!code-cpp[concrt-dataflow-agent#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_7.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
Control-flow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
Dataflow agent:
There are 500523 negative numbers.
There are 499477 positive numbers.
```

### <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`dataflow-agent.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc dataflow-agent.cpp**

[[トップ](#top)]

##  <a name="logging"></a> メッセージ ログ エージェントを作成します。

次の例では、`log_agent` クラスに似た `dataflow_agent` クラスを示します。 `log_agent` クラスは、ログ メッセージをファイルおよびコンソールに書き込む非同期ログ エージェントを実装します。 `log_agent` クラスは、アプリケーションがメッセージを情報、警告、またはエラーとして分類できるようにします。 また、アプリケーションが各ログ カテゴリをファイルとコンソールのどちらに書き込むか、または両方に書き込むかを指定できるようにします。 この例では、ファイルにすべてのログ メッセージが書き込まれ、コンソールにはエラー メッセージのみが書き込まれます。

[!code-cpp[concrt-log-filter#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-dataflow-agent_8.cpp)]

この例では、次の出力がコンソールに書き込まれます。

```Output
error: This is a sample error message.
```

また、次のテキストを含む log.txt ファイルが生成されます。

```Output
info: ===Logging started.===
warning: This is a sample warning message.
error: This is a sample error message.
info: ===Logging finished.===
```

### <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`log-filter.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc log-filter.cpp**

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)

