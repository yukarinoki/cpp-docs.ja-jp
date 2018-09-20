---
title: 'チュートリアル: デッドロックの防止への参加の使用 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- preventing deadlock with joins [Concurrency Runtime]
- deadlock, preventing [Concurrency Runtime]
- non-greedy joins, example
- join class, example
ms.assetid: d791f697-bb93-463e-84bd-5df1651b7446
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 45669b4838925ed671646ca1aad16a3fdbe6de77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46377280"
---
# <a name="walkthrough-using-join-to-prevent-deadlock"></a>チュートリアル: join を使用したデッドロックの防止

このトピックでは、食事する哲学者の問題を使用して、使用する方法を説明するために、 [concurrency::join](../../parallel/concrt/reference/join-class.md)アプリケーションでデッドロックを防止するクラス。 ソフトウェア アプリケーションで、2 つ以上のプロセスがそれぞれリソースを確保し、別のプロセスがリソースを解放するのをお互いに待機すると、*デッドロック*が発生します。

"食事する哲学者の問題" は、リソース セットが複数の同時実行プロセス間で共有される場合に発生する可能性のある一般的な問題の特定の例です。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のトピックを参照してください。

- [非同期エージェント](../../parallel/concrt/asynchronous-agents.md)

- [チュートリアル: エージェント ベースのアプリケーションの作成](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)

- [同期データ構造](../../parallel/concrt/synchronization-data-structures.md)

##  <a name="top"></a> セクション

このチュートリアルは、次のセクションで構成されています。

- [食事する哲学者の問題](#problem)

- [単純な実装](#deadlock)

- [デッドロックの防止に結合を使用します。](#solution)

##  <a name="problem"></a> 食事する哲学者の問題

"食事する哲学者の問題" は、アプリケーションでどのようにデッドロックが発生するかを示します。 この問題では、5 人の哲学者が丸いテーブルを囲んで座っています。 どの哲学者も思索と食事を交互に行っています。 どの哲学者も左隣の哲学者と 1 本の箸を共有する必要があり、また右隣の哲学者とも別の 1 本の箸を共有する必要があります。 次の図は、この配置を表しています。

![食事する哲学者の問題](../../parallel/concrt/media/dining_philosophersproblem.png "dining_philosophersproblem")

食事をするには、哲学者は 2 本の箸を持つ必要があります。 すべての哲学者が 1 本の箸を持ち、もう 1 本の箸を待つと、どの哲学者も食事することができず、すべての哲学者が餓死することになります。

[[トップ](#top)]

##  <a name="deadlock"></a> 単純な実装

次の例は、"食事する哲学者の問題" を考慮していない実装を示しています。 `philosopher`から派生したクラス[concurrency::agent](../../parallel/concrt/reference/agent-class.md)、各哲学者は独立して機能を有効にします。 例は、一連の共有を使用して[concurrency::critical_section](../../parallel/concrt/reference/critical-section-class.md)オブジェクトに、それぞれ`philosopher`本の箸への排他アクセスのオブジェクトします。

この実装を図に関連付けて説明すると、`philosopher` クラスは 1 人の哲学者を表します。 `int` 変数は、それぞれの箸を表します。 `critical_section` オブジェクトは、箸が置かれる箸置きとして機能します。 `run` メソッドは、哲学者の生命をシミュレートしています。 `think` メソッドは、考える行為をシミュレートしており、`eat` メソッドは、食事する行為をシミュレートしています。

`philosopher` オブジェクトは、`critical_section` メソッドを呼び出す前に、両方の `eat` オブジェクトをロックして、箸置きから箸が取られたことをシミュレートします。 `eat` の呼び出しの後、`philosopher` オブジェクトは、`critical_section` オブジェクトをロック解除状態に再設定することで、箸を箸置きに戻します。

`pickup_chopsticks` メソッドは、どこでデッドロックが発生する可能性があるかを示します。 すべての `philosopher` オブジェクトがいずれかのロックにアクセスした場合、どの `philosopher` オブジェクトも続行できません。これは、そのアクセスしたロックが別の `philosopher` オブジェクトにより制御されているためです。

## <a name="example"></a>例

### <a name="description"></a>説明

### <a name="code"></a>コード

[!code-cpp[concrt-philosophers-deadlock#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_1.cpp)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`philosophers-deadlock.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc philosophers-deadlock.cpp**

[[トップ](#top)]

##  <a name="solution"></a> デッドロックの防止に結合を使用します。

このセクションでは、メッセージ バッファーおよびメッセージ パッシング関数を使用して、デッドロックを発生させないようにする方法について説明します。

関連付ける前に、この例を`philosopher`クラス置き換える`critical_section`オブジェクトを使用して、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)オブジェクトと`join`オブジェクト。 `join` オブジェクトは、哲学者に箸を与える決定者として機能します。

この例では、`unbounded_buffer` クラスを使用しています。これは、ターゲットが `unbounded_buffer` オブジェクトからメッセージを受け取ったときに、そのメッセージはメッセージ キューから削除されるためです。 これにより、メッセージを保持する `unbounded_buffer` オブジェクトは、箸が使用できることを示すことができます。 メッセージを保持しない `unbounded_buffer` オブジェクトは、箸が使用されていることを示します。

この例では、最短一致の `join` オブジェクトを使用しています。最短一致の join は、両方の `philosopher` オブジェクトにメッセージが含まれる場合に限り、各 `unbounded_buffer` オブジェクトに対し、両方の箸へのアクセス権を与えるためです。 最長一致の join は、メッセージが使用できるようになるとすぐにメッセージを受け取るため、最長一致の join ではデッドロックは防止されません。 すべての最長一致 `join` オブジェクトがメッセージのいずれかを受け取り、一方で他のメッセージが使用できるようになるのを長時間待つ場合、デッドロックが発生する可能性があります。

最長一致と最短一致の結合、およびメッセージ バッファーのさまざまな種類の違いの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。

#### <a name="to-prevent-deadlock-in-this-example"></a>この例でデッドロックを防止するには

1. 次のコードを例から削除します。

[!code-cpp[concrt-philosophers-deadlock#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_2.cpp)]

1. `_left` クラスの `_right` データ メンバーおよび `philosopher` データ メンバーの型を `unbounded_buffer` に変更します。

[!code-cpp[concrt-philosophers-join#2](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_3.cpp)]

1. `philosopher` コンストラクターを変更して、パラメーターとして `unbounded_buffer` オブジェクトを受け取るようにします。

[!code-cpp[concrt-philosophers-join#3](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_4.cpp)]

1. `pickup_chopsticks` メソッドを変更して、最短一致の `join` オブジェクトを使用して両方の箸のメッセージ バッファーからメッセージを受け取るようにします。

[!code-cpp[concrt-philosophers-join#4](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_5.cpp)]

1. `putdown_chopsticks` メソッドを変更して、両方の箸のメッセージ バッファーにメッセージを送信することで、箸へのアクセス権を放棄するようにします。

[!code-cpp[concrt-philosophers-join#5](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_6.cpp)]

1. `run` メソッドを変更して、`pickup_chopsticks` メソッドの結果を保持し、それらの結果を `putdown_chopsticks` メソッドに渡すようにします。

[!code-cpp[concrt-philosophers-join#6](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_7.cpp)]

1. `chopsticks` 関数の `wmain` 変数の宣言を変更して、それぞれが 1 つのメッセージを保持する `unbounded_buffer` オブジェクトの配列にします。

[!code-cpp[concrt-philosophers-join#7](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_8.cpp)]

## <a name="example"></a>例

### <a name="description"></a>説明

最短一致の `join` オブジェクトを使用してデッドロックの危険性を排除する完全な例を次に示します。

### <a name="code"></a>コード

[!code-cpp[concrt-philosophers-join#1](../../parallel/concrt/codesnippet/cpp/walkthrough-using-join-to-prevent-deadlock_9.cpp)]

### <a name="comments"></a>コメント

この例を実行すると、次の出力が生成されます。

```Output
aristotle ate 50 times.
descartes ate 50 times.
hobbes ate 50 times.
socrates ate 50 times.
plato ate 50 times.
```

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるか、という名前のファイルに貼り付ける`philosophers-join.cpp`Visual Studio コマンド プロンプト ウィンドウで、次のコマンドを実行します。

**cl.exe/EHsc philosophers-join.cpp**

[[トップ](#top)]

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)<br/>
[非同期エージェント](../../parallel/concrt/asynchronous-agents.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)<br/>
[同期データ構造](../../parallel/concrt/synchronization-data-structures.md)
