---
title: 'チュートリアル: カスタム メッセージ ブロックの作成 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f9391d99f75bdb5ac2191a65e525ce989aefcd6b
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/19/2018
ms.locfileid: "46421285"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>チュートリアル: カスタム メッセージ ブロックの作成

ここでは、受信メッセージを優先順位に従って並べるカスタム メッセージ ブロックの型を作成する方法について説明します。

組み込みのメッセージ ブロックの型には幅広い機能が備わっていますが、独自のメッセージ ブロックの型を作成して、アプリケーションの要件を満たすようにカスタマイズすることもできます。 非同期エージェント ライブラリによって提供される組み込みのメッセージ ブロックの型の説明は、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="prerequisites"></a>必須コンポーネント

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)

##  <a name="top"></a> セクション

このチュートリアルは、次のセクションで構成されています。

- [カスタム メッセージ ブロックのデザイン](#design)

- [Priority_buffer クラスの定義](#class)

- [コード例全体](#complete)

##  <a name="design"></a> カスタム メッセージ ブロックのデザイン

メッセージ ブロックは、メッセージの送受信処理に参加します。 メッセージを送信するメッセージ ブロックと呼ばれる、*ソース ブロック*します。 メッセージを受信するメッセージ ブロックと呼ばれる、*ターゲット ブロック*します。 メッセージを送受信するメッセージ ブロックと呼ばれる、*伝達子ブロック*します。 エージェント ライブラリは、抽象クラスを使用して[concurrency::isource](../../parallel/concrt/reference/isource-class.md)ソース ブロックと抽象クラスを表す[concurrency::itarget](../../parallel/concrt/reference/itarget-class.md)ターゲット ブロックを表します。 ソースとして機能するメッセージ ブロックの型は `ISource` から派生します。ターゲットとして機能するメッセージ ブロックの型は `ITarget` から派生します。

メッセージ ブロックの型は `ISource` および `ITarget` から直接派生させることもできますが、エージェント ライブラリには、メッセージ ブロックのすべての型に共通の大部分の機能を実行する 3 つの基底クラスが定義されています。これらの基底クラスによって、エラーの処理やメッセージ ブロックの接続などの操作が同時実行セーフに行われます。 [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md)クラスから派生`ISource`他のブロックにメッセージを送信します。 [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md)クラスから派生`ITarget`と他のブロックからメッセージを受信します。 [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md)クラスから派生`ISource`と`ITarget`と他のブロックにメッセージを送信しますが、他のブロックからメッセージを受信します。 メッセージ ブロックの動作に焦点を合わせることができるように、インフラストラクチャの細部の処理にはこれらの 3 つの基底クラスを使用することをお勧めします。

`source_block`、`target_block`、および `propagator_block` の各クラスはテンプレートであり、ソース ブロックとターゲット ブロック間の接続 (リンク) を管理する型、およびメッセージの処理方法を管理する型でパラメーター化されます。 エージェント ライブラリは、リンクの管理を実行する 2 つの型を定義します。 [concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md)と[concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md)します。 `single_link_registry` クラスは、メッセージ ブロックを 1 つのソースまたは 1 つのターゲットにリンクできるようにします。 `multi_link_registry` クラスは、メッセージ ブロックを複数のソースまたは複数のターゲットにリンクできるようにします。 エージェント ライブラリは、メッセージの管理を実行する 1 つのクラスを定義します。 [concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md)します。 `ordered_message_processor` クラスは、メッセージ ブロックでメッセージを受信順に処理できるようにします。

メッセージ ブロックとソースおよびターゲットとの相互関係をより深く理解できるように、次の例を考えてみてください。 この例の宣言を示しています、 [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)クラス。

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` クラスは `propagator_block` から派生するため、ソース ブロックとしてもターゲット ブロックとしても機能します。 `_Input` 型のメッセージを受け入れ、`_Output` 型のメッセージを送信します。 `transformer` クラスは、`single_link_registry` をターゲット ブロックのリンク マネージャーとして指定し、`multi_link_registry` をソース ブロックのリンク マネージャーとして指定します。 したがって、`transformer` オブジェクトで許容されるターゲットは 1 つだけですが、ソースの数に制限はありません。

派生したクラス`source_block`6 つのメソッドを実装する必要があります: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets)、 [accept_message](reference/source-block-class.md#accept_message)、 [reserve_message](reference/source-block-class.md#reserve_message)、 [consume_message](reference/source-block-class.md#consume_message)、 [release_message](reference/source-block-class.md#release_message)、および[resume_propagation](reference/source-block-class.md#resume_propagation)します。 派生したクラス`target_block`実装する必要があります、 [propagate_message](reference/propagator-block-class.md#propagate_message)メソッドおよび実装できます必要に応じて、 [send_message](reference/propagator-block-class.md#send_message)メソッド。 `propagator_block` からの派生は、`source_block` および `target_block` からの派生と機能的には同等です。

`propagate_to_any_targets` メソッドは、受信メッセージを非同期的または同期的に処理し、送信メッセージを伝達するためにランタイムによって呼び出されます。 `accept_message` メソッドは、メッセージを受け入れるためにターゲット ブロックによって呼び出されます。 `unbounded_buffer` などのメッセージ ブロックの型の多くは、最初にメッセージを受信するターゲットにのみメッセージを送信します。 したがって、メッセージの所有権はそのターゲットに譲渡されます。 などの他のメッセージ ブロック型[concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)、各ターゲット ブロックにメッセージを提供します。 したがって、`overwrite_buffer` は各ターゲット用にメッセージのコピーを作成します。

`reserve_message`、`consume_message`、`release_message`、および `resume_propagation` メソッドは、メッセージ ブロックがメッセージの予約に参加できるようにします。 ターゲット ブロックは、提供されたメッセージを予約して後で使用できるようにする場合に、`reserve_message` メソッドを呼び出します。 メッセージを受信したターゲット ブロックは、`consume_message` メソッドを呼び出してそのメッセージを処理するか、`release_message` メソッドを呼び出して予約を取り消すことができます。 `accept_message` メソッドと同様に、`consume_message` の実装では、メッセージの所有権を譲渡するか、メッセージのコピーを返すことができます。 ターゲット ブロックが予約済みのメッセージを処理または解放すると、ランタイムは `resume_propagation` メソッドを呼び出します。 通常、このメソッドは、キュー内の次のメッセージからメッセージ伝達を続行します。

ランタイムは、`propagate_message` メソッドを呼び出して、別のブロックから現在のブロックにメッセージを非同期的に転送します。 `send_message` メソッドは、非同期的にではなく同期的にメッセージをターゲット ブロックに送信する点を除いて、`propagate_message` と似ています。 `send_message` の既定の実装では、すべての受信メッセージが拒否されます。 ターゲット ブロックに関連付けられているオプションのフィルター関数をメッセージが通過しない場合、ランタイムはどちらのメソッドも呼び出しません。 メッセージ フィルターの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。

[[トップ](#top)]

##  <a name="class"></a> Priority_buffer クラスの定義

`priority_buffer` クラスは、受信メッセージを優先順位に従って並べてから、メッセージの受信順に並べるカスタム メッセージ ブロックの型です。 `priority_buffer`クラスに似ています、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)メッセージのキューを保持するためのクラスともには、ソースとターゲット メッセージ ブロックの両方として機能し、複数のソースと複数の両方を持つことができますので、対象とします。 ただし、`unbounded_buffer` でのメッセージの伝達順は、必ずソースからのメッセージの受信順になります。

`priority_buffer`クラス型のメッセージを受信する std::[タプル](../../standard-library/tuple-class.md)が含まれている`PriorityType`と`Type`要素。 `PriorityType` は各メッセージの優先順位を保持する型を表し、`Type` はメッセージのデータ部分を表します。 `priority_buffer` クラスは、`Type` 型のメッセージを送信します。 `priority_buffer`クラスは、2 つのメッセージ キューも管理: [:priority_queue](../../standard-library/priority-queue-class.md)受信メッセージのオブジェクトと、std::[キュー](../../standard-library/queue-class.md)送信メッセージのオブジェクト。 `priority_buffer` オブジェクトが複数のメッセージを同時に受信する場合、またはコンシューマーがまだメッセージを読み取っていないときに複数のメッセージを受信する場合、メッセージを優先順位に従って並べ替えると便利です。

`propagator_block` クラスでは、`priority_buffer` の派生クラスで実装する必要のある 7 つのメソッドに加えて、`link_target_notification` メソッドと `send_message` メソッドもオーバーライドします。 `priority_buffer` クラスでは、2 つのパブリック ヘルパー メソッド (`enqueue` および `dequeue`) と 1 つのプライベート ヘルパー メソッド (`propagate_priority_order`) も定義します。

次の手順では、`priority_buffer` クラスを実装する方法について説明します。

#### <a name="to-define-the-prioritybuffer-class"></a>priority_buffer クラスを定義するには

1. C++ ヘッダー ファイルを作成し、名前`priority_buffer.h`します。 または、プロジェクトに含まれる既存のヘッダー ファイルを使用することもできます。

1. `priority_buffer.h`、次のコードを追加します。

[!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. `std`名前空間の特殊化を定義する[std::less](../../standard-library/less-struct.md)と[std::greater](../../standard-library/greater-struct.md)同時実行に対して作用する::[メッセージ](../../parallel/concrt/reference/message-class.md)オブジェクト。

[!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

     The `priority_buffer` class stores `message` objects in a `priority_queue` object. These type specializations enable the priority queue to sort messages according to their priority. The priority is the first element of the `tuple` object.

1. `concurrencyex` 名前空間で、`priority_buffer` クラスを宣言します。

[!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

     The `priority_buffer` class derives from `propagator_block`. Therefore, it can both send and receive messages. The `priority_buffer` class can have multiple targets that receive messages of type `Type`. It can also have multiple sources that send messages of type `tuple<PriorityType, Type>`.

1. `private` クラスの `priority_buffer` セクションに、次のメンバー変数を追加します。

[!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

     The `priority_queue` object holds incoming messages; the `queue` object holds outgoing messages. A `priority_buffer` object can receive multiple messages simultaneously; the `critical_section` object synchronizes access to the queue of input messages.

1. `private` セクションで、コピー コンストラクターと代入演算子を定義します。 これにより、`priority_queue` オブジェクトが割り当て可能になるのを防ぎます。

[!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. `public` セクションで、多くのメッセージ ブロックの型に共通のコンストラクターを定義します。 デストラクターも定義します。

[!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. `public` セクションで、`enqueue` メソッドと `dequeue` メソッドを定義します。 これらのヘルパー メソッドによって、`priority_buffer` オブジェクトとの間でメッセージを送受信する別の手段が提供されます。

[!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

9. `protected` セクションで、`propagate_to_any_targets` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

     The `propagate_to_any_targets` method transfers the message that is at the front of the input queue to the output queue and propagates out all messages in the output queue.

10. `protected` セクションで、`accept_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

     When a target block calls the `accept_message` method, the `priority_buffer` class transfers ownership of the message to the first target block that accepts it. (This resembles the behavior of `unbounded_buffer`.)

11. `protected` セクションで、`reserve_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

     The `priority_buffer` class permits a target block to reserve a message when the provided message identifier matches the identifier of the message that is at the front of the queue. In other words, a target can reserve the message if the `priority_buffer` object has not yet received an additional message and has not yet  propagated out the current one.

12. `protected` セクションで、`consume_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

     A target block calls `consume_message` to transfer ownership of the message that it reserved.

13. `protected` セクションで、`release_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

     A target block calls `release_message` to cancel its reservation to a message.

14. `protected` セクションで、`resume_propagation` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

     The runtime calls `resume_propagation` after a target block either consumes or releases a reserved message. This method propagates out any messages that are in the output queue.

15. `protected` セクションで、`link_target_notification` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

     The `_M_pReservedFor` member variable is defined by the base class, `source_block`. This member variable points to the target block, if any, that is holding a reservation to the message that is at the front of the output queue. The runtime calls `link_target_notification` when a new target is linked to the `priority_buffer` object. This method propagates out any messages that are in the output queue if no target is holding a reservation.

16. `private` セクションで、`propagate_priority_order` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

     This method propagates out all messages from the output queue. Every message in the queue is offered to every target block until one of the target blocks accepts the message. The `priority_buffer` class preserves the order of the outgoing messages. Therefore, the first message in the output queue must be accepted by a target block before this method offers any other message to the target blocks.

17. `protected` セクションで、`propagate_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

     The `propagate_message` method enables the `priority_buffer` class to act as a message receiver, or target. This method receives the message that is offered by the provided source block and inserts that message into the priority queue. The `propagate_message` method then asynchronously sends all output messages to the target blocks.

     The runtime calls this method when you call the [concurrency::asend](reference/concurrency-namespace-functions.md#asend) function or when the message block is connected to other message blocks.

18. `protected` セクションで、`send_message` メソッドを定義します。

[!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

     The `send_message` method resembles `propagate_message`. However it sends the output messages synchronously instead of asynchronously.

     The runtime calls this method during a synchronous send operation, such as when you call the [concurrency::send](reference/concurrency-namespace-functions.md#send) function.

`priority_buffer` クラスには、多くのメッセージ ブロックの型に共通のコンストラクター オーバーロードが含まれています。 一部のコンス トラクター オーバー ロード[concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)または[concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)オブジェクトで、特定のタスク スケジューラで管理するためのメッセージ ブロックを有効にします。 フィルター関数を受け取るコンストラクター オーバーロードもあります。 フィルター関数を使用すると、メッセージ ブロックでのメッセージの受け入れまたは拒否をメッセージ ペイロードに基づいて行うことができます。 メッセージ フィルターの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)します。 タスク スケジューラに関する詳細については、次を参照してください。[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)します。

`priority_buffer`クラスは、優先度でメッセージを注文し、メッセージが受信される順序でこのクラスは、最も役に立つを受信したときのメッセージ、非同期的になどを呼び出すとき、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)関数または他のメッセージ ブロックにメッセージ ブロックを接続するとき。

[[トップ](#top)]

##  <a name="complete"></a> 完全な例

次の例では、`priority_buffer` クラスの完全な定義を示します。

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

次の例では、多数の同時に実行します`asend`と[concurrency::receive](reference/concurrency-namespace-functions.md#receive)に対する操作を`priority_buffer`オブジェクト。

[!code-cpp[concrt-priority-buffer#19](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_20.cpp)]

この例では、次のサンプル出力が生成されます。

```Output
36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36 36
24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24 24
12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12 12
```

`priority_buffer` クラスは、メッセージを優先順位に従って並べてから、メッセージの受信順に並べます。 この例では、優先順位を示す数値が大きいメッセージほど、キューの先頭近くに挿入されています。

[[トップ](#top)]

## <a name="compiling-the-code"></a>コードのコンパイル

コード例をコピーし、Visual Studio プロジェクトに貼り付けるかの定義を貼り付け、`priority_buffer`という名前のファイル内のクラス`priority_buffer.h`という名前のファイルで、テスト プログラム`priority_buffer.cpp`Visual Studio で、次のコマンドを実行しますコマンド プロンプト ウィンドウです。

**cl.exe/EHsc priority_buffer.cpp**

## <a name="see-also"></a>関連項目

[コンカレンシー ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)
