---
title: 'チュートリアル: カスタム メッセージ ブロックの作成'
ms.date: 04/25/2019
helpviewer_keywords:
- creating custom message blocks Concurrency Runtime]
- custom message blocks, creating [Concurrency Runtime]
ms.assetid: 4c6477ad-613c-4cac-8e94-2c9e63cd43a1
ms.openlocfilehash: 3386994dce68812cf3ed0852a24d8910cb903acf
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368560"
---
# <a name="walkthrough-creating-a-custom-message-block"></a>チュートリアル: カスタム メッセージ ブロックの作成

ここでは、受信メッセージを優先順位に従って並べるカスタム メッセージ ブロックの型を作成する方法について説明します。

組み込みのメッセージ ブロックの型には幅広い機能が備わっていますが、独自のメッセージ ブロックの型を作成して、アプリケーションの要件を満たすようにカスタマイズすることもできます。 非同期エージェント ライブラリによって提供される組み込みのメッセージ ブロックの種類の説明については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="prerequisites"></a>前提条件

このチュートリアルを開始する前に、次のドキュメントを参照してください。

- [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)

- [メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)

## <a name="sections"></a><a name="top"></a>セクション

このチュートリアルは、次のセクションで構成されています。

- [カスタム メッセージ ブロックのデザイン](#design)

- [priority_buffer クラスの定義](#class)

- [完全な例](#complete)

## <a name="designing-a-custom-message-block"></a><a name="design"></a>カスタム メッセージ ブロックの設計

メッセージ ブロックは、メッセージの送受信処理に参加します。 メッセージを送信するメッセージ ブロックは、*ソース ブロック*と呼ばれます。 メッセージを受信するメッセージ ブロックは *、ターゲット ブロック*と呼ばれます。 メッセージを送受信するメッセージ ブロックは、*プロパゲーター ブロック*と呼ばれます。 エージェント ライブラリは、抽象クラス[の同時実行性::ISource](../../parallel/concrt/reference/isource-class.md)を使用してソース ブロックを表し、抽象クラス[の同時実行性::ITarget](../../parallel/concrt/reference/itarget-class.md)を使用してターゲット ブロックを表します。 ソースとして機能するメッセージ ブロックの型は `ISource` から派生します。ターゲットとして機能するメッセージ ブロックの型は `ITarget` から派生します。

メッセージ ブロックの型は `ISource` および `ITarget` から直接派生させることもできますが、エージェント ライブラリには、メッセージ ブロックのすべての型に共通の大部分の機能を実行する 3 つの基底クラスが定義されています。これらの基底クラスによって、エラーの処理やメッセージ ブロックの接続などの操作がコンカレンシー セーフに行われます。 [同時実行::source_block](../../parallel/concrt/reference/source-block-class.md)クラスは、他`ISource`のブロックから派生し、メッセージを送信します。 [同時実行::target_block](../../parallel/concrt/reference/target-block-class.md)クラスは、他`ITarget`のブロックからメッセージを派生し、受信します。 [同時実行::propagator_block](../../parallel/concrt/reference/propagator-block-class.md)クラスは、他の`ISource`ブロック`ITarget`から派生してメッセージを送信し、他のブロックからメッセージを受信します。 メッセージ ブロックの動作に焦点を合わせることができるように、インフラストラクチャの細部の処理にはこれらの 3 つの基底クラスを使用することをお勧めします。

`source_block`、`target_block`、および `propagator_block` の各クラスはテンプレートであり、ソース ブロックとターゲット ブロック間の接続 (リンク) を管理する型、およびメッセージの処理方法を管理する型でパラメーター化されます。 エージェント ライブラリは、リンク管理を実行する 2 つの型を定義します[multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md) [single_link_registry。](../../parallel/concrt/reference/single-link-registry-class.md) `single_link_registry` クラスは、メッセージ ブロックを 1 つのソースまたは 1 つのターゲットにリンクできるようにします。 `multi_link_registry` クラスは、メッセージ ブロックを複数のソースまたは複数のターゲットにリンクできるようにします。 エージェント ライブラリは、メッセージ管理を実行する 1 つのクラスを定義します[ordered_message_processor。](../../parallel/concrt/reference/ordered-message-processor-class.md) `ordered_message_processor` クラスは、メッセージ ブロックでメッセージを受信順に処理できるようにします。

メッセージ ブロックとソースおよびターゲットとの相互関係をより深く理解できるように、次の例を考えてみてください。 この例では、[同時実行::transformer](../../parallel/concrt/reference/transformer-class.md)クラスの宣言を示します。

[!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]

`transformer` クラスは `propagator_block` から派生するため、ソース ブロックとしてもターゲット ブロックとしても機能します。 `_Input` 型のメッセージを受け入れ、`_Output` 型のメッセージを送信します。 `transformer` クラスは、`single_link_registry` をターゲット ブロックのリンク マネージャーとして指定し、`multi_link_registry` をソース ブロックのリンク マネージャーとして指定します。 したがって、`transformer` オブジェクトで許容されるターゲットは 1 つだけですが、ソースの数に制限はありません。

派生`source_block`元のクラスには[、propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets) [、accept_message、reserve_message](reference/source-block-class.md#accept_message) [、consume_message](reference/source-block-class.md#consume_message) [、release_message](reference/source-block-class.md#release_message)、および[resume_propagation](reference/source-block-class.md#resume_propagation)の 6 つのメソッドが実装されている必要があります。 [reserve_message](reference/source-block-class.md#reserve_message) 派生元のクラスは`target_block`[、propagate_message](reference/propagator-block-class.md#propagate_message)メソッドを実装する必要があり、オプションで[send_message](reference/propagator-block-class.md#send_message)メソッドを実装できます。 `propagator_block` からの派生は、`source_block` および `target_block` からの派生と機能的には同等です。

`propagate_to_any_targets` メソッドは、受信メッセージを非同期的または同期的に処理し、送信メッセージを伝達するためにランタイムによって呼び出されます。 `accept_message` メソッドは、メッセージを受け入れるためにターゲット ブロックによって呼び出されます。 `unbounded_buffer` などのメッセージ ブロックの型の多くは、最初にメッセージを受信するターゲットにのみメッセージを送信します。 したがって、メッセージの所有権はそのターゲットに譲渡されます。 [同時実行::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)などの他のメッセージ ブロック型は、そのターゲット ブロックのそれぞれにメッセージを提供します。 したがって、`overwrite_buffer` は各ターゲット用にメッセージのコピーを作成します。

`reserve_message`、`consume_message`、`release_message`、および `resume_propagation` メソッドは、メッセージ ブロックがメッセージの予約に参加できるようにします。 ターゲット ブロックは、提供されたメッセージを予約して後で使用できるようにする場合に、`reserve_message` メソッドを呼び出します。 メッセージを受信したターゲット ブロックは、`consume_message` メソッドを呼び出してそのメッセージを処理するか、`release_message` メソッドを呼び出して予約を取り消すことができます。 `accept_message` メソッドと同様に、`consume_message` の実装では、メッセージの所有権を譲渡するか、メッセージのコピーを返すことができます。 ターゲット ブロックが予約済みのメッセージを処理または解放すると、ランタイムは `resume_propagation` メソッドを呼び出します。 通常、このメソッドは、キュー内の次のメッセージからメッセージ伝達を続行します。

ランタイムは、`propagate_message` メソッドを呼び出して、別のブロックから現在のブロックにメッセージを非同期的に転送します。 `send_message` メソッドは、非同期的にではなく同期的にメッセージをターゲット ブロックに送信する点を除いて、`propagate_message` と似ています。 `send_message` の既定の実装では、すべての受信メッセージが拒否されます。 ターゲット ブロックに関連付けられているオプションのフィルター関数をメッセージが通過しない場合、ランタイムはどちらのメソッドも呼び出しません。 メッセージ フィルタの詳細については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

[[トップ](#top)]

## <a name="defining-the-priority_buffer-class"></a><a name="class"></a>priority_buffer クラスの定義

`priority_buffer` クラスは、受信メッセージを優先順位に従って並べてから、メッセージの受信順に並べるカスタム メッセージ ブロックの型です。 この`priority_buffer`クラスは、メッセージのキューを保持するため、およびソースとターゲットの両方のメッセージ ブロックとして機能し、複数のソースと複数のターゲットの両方を持つことができるため、[同時実行::unbounded_buffer](reference/unbounded-buffer-class.md)クラスに似ています。 ただし、`unbounded_buffer` でのメッセージの伝達順は、必ずソースからのメッセージの受信順になります。

クラス`priority_buffer`は、要素を含`PriorityType`む std::[タプル](../../standard-library/tuple-class.md)型の`Type`メッセージを受け取ります。 `PriorityType` は各メッセージの優先順位を保持する型を表し、`Type` はメッセージのデータ部分を表します。 `priority_buffer` クラスは、`Type` 型のメッセージを送信します。 この`priority_buffer`クラスは、受信メッセージの[std::priority_queue](../../standard-library/priority-queue-class.md)オブジェクトと、送信メッセージの std::[キュー](../../standard-library/queue-class.md)オブジェクトという 2 つのメッセージ キューも管理します。 `priority_buffer` オブジェクトが複数のメッセージを同時に受信する場合、またはコンシューマーがまだメッセージを読み取っていないときに複数のメッセージを受信する場合、メッセージを優先順位に従って並べ替えると便利です。

`propagator_block` クラスでは、`priority_buffer` の派生クラスで実装する必要のある 7 つのメソッドに加えて、`link_target_notification` メソッドと `send_message` メソッドもオーバーライドします。 `priority_buffer` クラスでは、2 つのパブリック ヘルパー メソッド (`enqueue` および `dequeue`) と 1 つのプライベート ヘルパー メソッド (`propagate_priority_order`) も定義します。

次の手順では、`priority_buffer` クラスを実装する方法について説明します。

#### <a name="to-define-the-priority_buffer-class"></a>priority_buffer クラスを定義するには

1. C++ ヘッダー ファイルを作成し`priority_buffer.h`、 という名前を付けます。 または、プロジェクトに含まれる既存のヘッダー ファイルを使用することもできます。

1. で`priority_buffer.h`、次のコードを追加します。

    [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]

1. 名前空間で`std`、並行性::[メッセージ](../../parallel/concrt/reference/message-class.md)オブジェクトに対して動作する[std::less](../../standard-library/less-struct.md)と[std::greater](../../standard-library/greater-struct.md)の特殊化を定義します。

    [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]

   `priority_buffer` クラスは、`message` オブジェクトに `priority_queue` オブジェクトを格納します。 このような型の特殊化によって、優先順位キューでメッセージが優先順位に従って並べ替えられるようになります。 優先順位は、`tuple` オブジェクトの最初の要素です。

1. `concurrencyex` 名前空間で、`priority_buffer` クラスを宣言します。

    [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]

   `priority_buffer` クラスは `propagator_block` から派生したものです。 したがって、メッセージを送信することも受信することもできます。 `priority_buffer` クラスは、`Type` 型のメッセージを受信する複数のターゲットを持つことができます。 さらに、`tuple<PriorityType, Type>` 型のメッセージを送信する複数のソースを持つことができます。

1. `private` クラスの `priority_buffer` セクションに、次のメンバー変数を追加します。

    [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]

   `priority_queue` オブジェクトは受信メッセージを保持し、`queue` オブジェクトは送信メッセージを保持します。 `priority_buffer` オブジェクトは、複数のメッセージを同時に受信できます。`critical_section` オブジェクトは、入力メッセージのキューへのアクセスを同期します。

1. `private` セクションで、コピー コンストラクターと代入演算子を定義します。 これにより、`priority_queue` オブジェクトが割り当て可能になるのを防ぎます。

    [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]

1. `public` セクションで、多くのメッセージ ブロックの型に共通のコンストラクターを定義します。 デストラクターも定義します。

    [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]

1. `public` セクションで、`enqueue` メソッドと `dequeue` メソッドを定義します。 これらのヘルパー メソッドによって、`priority_buffer` オブジェクトとの間でメッセージを送受信する別の手段が提供されます。

    [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]

1. `protected` セクションで、`propagate_to_any_targets` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]

   `propagate_to_any_targets` メソッドは、入力キューの先頭にあるメッセージを出力キューに転送し、出力キュー内のすべてのメッセージを伝達します。

1. `protected` セクションで、`accept_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]

   ターゲット ブロックから `accept_message` メソッドが呼び出されたとき、`priority_buffer` クラスは、メッセージを最初に受け入れるターゲット ブロックにそのメッセージの所有権を譲渡します  (この動作は `unbounded_buffer` の動作と似ています)。

1. `protected` セクションで、`reserve_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]

   `priority_buffer` クラスは、指定されたメッセージ識別子とキューの先頭にあるメッセージの識別子が一致する場合に、ターゲット ブロックでメッセージを予約できるようにします。 つまり、`priority_buffer` オブジェクトがまだ追加のメッセージを受信しておらず、現在のメッセージも伝達していない場合、ターゲットはメッセージを予約できます。

1. `protected` セクションで、`consume_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]

   ターゲット ブロックは、予約したメッセージの所有権を譲渡するために `consume_message` を呼び出します。

1. `protected` セクションで、`release_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]

   ターゲット ブロックは、メッセージの予約を取り消すために `release_message` を呼び出します。

1. `protected` セクションで、`resume_propagation` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]

   ターゲット ブロックが予約済みのメッセージを処理または解放すると、ランタイムは `resume_propagation` を呼び出します。 このメソッドは、出力キュー内のすべてのメッセージを伝達します。

1. `protected` セクションで、`link_target_notification` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]

   `_M_pReservedFor` メンバー変数は、`source_block` 基底クラスによって定義されます。 このメンバー変数は、出力キューの先頭にあるメッセージの予約を保持しているターゲット ブロック (存在する場合) を指します。 新しいターゲットが `link_target_notification` オブジェクトにリンクされると、ランタイムは `priority_buffer` を呼び出します。 このメソッドは、ターゲットが予約を保持していない場合に、出力キュー内のすべてのメッセージを伝達します。

1. `private` セクションで、`propagate_priority_order` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]

   このメソッドは、出力キュー内のすべてのメッセージを伝達します。 ターゲット ブロックの 1 つがメッセージを受け入れるまで、キュー内の各メッセージが各ターゲット ブロックに提供されます。 `priority_buffer` クラスは、送信メッセージの順序を保持しています。 そこで、このメソッドでは、出力キュー内の最初のメッセージがいずれかのターゲット ブロックによって受け入れられるまで、他のメッセージをターゲット ブロックに提供しないようにします。

1. `protected` セクションで、`propagate_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]

   `propagate_message` メソッドは、`priority_buffer` クラスがメッセージの受信側 (つまりターゲット) として機能するようにします。 このメソッドは、指定されたソース ブロックから提供されたメッセージを受信し、そのメッセージを優先順位キューに挿入します。 その後、`propagate_message` メソッドは、すべての出力メッセージをターゲット ブロックに非同期的に送信します。

   [ランタイムは、同時実行関数](reference/concurrency-namespace-functions.md#asend)を呼び出すとき、またはメッセージ ブロックが他のメッセージ ブロックに接続されている場合に、このメソッドを呼び出します。

1. `protected` セクションで、`send_message` メソッドを定義します。

    [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]

   `send_message` メソッドは `propagate_message` と似ています。 ただし、このメソッドは、非同期的にではなく同期的に出力メッセージを送信します。

   ランタイムは、同期送信操作中にこのメソッドを呼び出します ([同時実行::send](reference/concurrency-namespace-functions.md#send)関数を呼び出す場合など)。

`priority_buffer` クラスには、多くのメッセージ ブロックの型に共通のコンストラクター オーバーロードが含まれています。 一部のコンストラクター オーバーロードは[、同時実行性を](../../parallel/concrt/reference/scheduler-class.md)受け取ります::スケジューラまたは[同時実行::ScheduleGroup](../../parallel/concrt/reference/schedulegroup-class.md)オブジェクトは、メッセージ ブロックを特定のタスク スケジューラで管理できるようにします。 フィルター関数を受け取るコンストラクター オーバーロードもあります。 フィルター関数を使用すると、メッセージ ブロックでのメッセージの受け入れまたは拒否をメッセージ ペイロードに基づいて行うことができます。 メッセージ フィルタの詳細については、「[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。 タスク スケジューラの詳細については、「[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)」を参照してください。

クラスは`priority_buffer`メッセージを優先順位で並べ、メッセージが受信される順序で並べ替えるので、このクラスは、メッセージを非同期で受信する場合 ([たとえば、同時実行::asend](reference/concurrency-namespace-functions.md#asend)関数を呼び出したときや、メッセージ ブロックが他のメッセージ ブロックに接続されている場合) に最も役立ちます。

[[トップ](#top)]

## <a name="the-complete-example"></a><a name="complete"></a>完全な例

次の例では、`priority_buffer` クラスの完全な定義を示します。

[!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]

次の例では、オブジェクトに対して`asend`同時[実行操作::receive](reference/concurrency-namespace-functions.md#receive)操作を`priority_buffer`同時に実行します。

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

サンプル コードをコピーして Visual Studio プロジェクトに貼り付けるか、`priority_buffer`クラスの定義を名前付き`priority_buffer.h`のファイルに貼り付け、テスト`priority_buffer.cpp`プログラムを名前が付いたファイルに貼り付け、Visual Studio コマンド プロンプト ウィンドウで次のコマンドを実行します。

**クエプ /EHsc priority_buffer.cpp**

## <a name="see-also"></a>関連項目

[同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)<br/>
[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)<br/>
[メッセージパッシング関数](../../parallel/concrt/message-passing-functions.md)
