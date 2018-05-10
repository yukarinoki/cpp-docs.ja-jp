---
title: 'チュートリアル: カスタム メッセージ ブロックの作成 |Microsoft ドキュメント'
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
ms.openlocfilehash: fa70cf40851815ff92f01405d47015afd2e3e444
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="walkthrough-creating-a-custom-message-block"></a>チュートリアル: カスタム メッセージ ブロックの作成
ここでは、受信メッセージを優先順位に従って並べるカスタム メッセージ ブロックの型を作成する方法について説明します。  
  
 組み込みのメッセージ ブロックの型には幅広い機能が備わっていますが、独自のメッセージ ブロックの型を作成して、アプリケーションの要件を満たすようにカスタマイズすることもできます。 非同期エージェント ライブラリによって提供される組み込みのメッセージ ブロックの型の説明は、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
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
 メッセージ ブロックは、メッセージの送受信処理に参加します。 メッセージを送信するメッセージ ブロックと呼ばれる、*ソース ブロック*です。 メッセージを受信するメッセージ ブロックと呼ばれる、*ターゲット ブロック*です。 メッセージを送受信するメッセージ ブロックと呼ばれる、*伝達子ブロック*です。 エージェント ライブラリは、抽象クラスを使用して[concurrency::isource](../../parallel/concrt/reference/isource-class.md)ソース ブロックと抽象クラスを表す[concurrency::itarget](../../parallel/concrt/reference/itarget-class.md)ターゲット ブロックを表します。 ソースとして機能するメッセージ ブロックの型は `ISource` から派生します。ターゲットとして機能するメッセージ ブロックの型は `ITarget` から派生します。  
  
 メッセージ ブロックの型は `ISource` および `ITarget` から直接派生させることもできますが、エージェント ライブラリには、メッセージ ブロックのすべての型に共通の大部分の機能を実行する 3 つの基底クラスが定義されています。これらの基底クラスによって、エラーの処理やメッセージ ブロックの接続などの操作が同時実行セーフに行われます。 [Concurrency::source_block](../../parallel/concrt/reference/source-block-class.md)クラスから派生`ISource`し、他のブロックにメッセージを送信します。 [Concurrency::target_block](../../parallel/concrt/reference/target-block-class.md)クラスから派生`ITarget`他のブロックからメッセージを受信します。 [Concurrency::propagator_block](../../parallel/concrt/reference/propagator-block-class.md)クラスから派生`ISource`と`ITarget`し、送信メッセージを他のブロックとそれには、他のブロックからメッセージを受信します。 メッセージ ブロックの動作に焦点を合わせることができるように、インフラストラクチャの細部の処理にはこれらの 3 つの基底クラスを使用することをお勧めします。  
  
 `source_block`、`target_block`、および `propagator_block` の各クラスはテンプレートであり、ソース ブロックとターゲット ブロック間の接続 (リンク) を管理する型、およびメッセージの処理方法を管理する型でパラメーター化されます。 エージェント ライブラリはリンクの管理を実行する 2 つの型を定義[concurrency::single_link_registry](../../parallel/concrt/reference/single-link-registry-class.md)と[concurrency::multi_link_registry](../../parallel/concrt/reference/multi-link-registry-class.md)です。 `single_link_registry` クラスは、メッセージ ブロックを 1 つのソースまたは 1 つのターゲットにリンクできるようにします。 `multi_link_registry` クラスは、メッセージ ブロックを複数のソースまたは複数のターゲットにリンクできるようにします。 エージェント ライブラリは、メッセージの管理を実行する 1 つのクラスを定義[concurrency::ordered_message_processor](../../parallel/concrt/reference/ordered-message-processor-class.md)です。 `ordered_message_processor` クラスは、メッセージ ブロックでメッセージを受信順に処理できるようにします。  
  
 メッセージ ブロックとソースおよびターゲットとの相互関係をより深く理解できるように、次の例を考えてみてください。 この例の宣言を示しています、 [concurrency::transformer](../../parallel/concrt/reference/transformer-class.md)クラスです。  
  
 [!code-cpp[concrt-priority-buffer#20](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_1.cpp)]  
  
 `transformer` クラスは `propagator_block` から派生するため、ソース ブロックとしてもターゲット ブロックとしても機能します。 `_Input` 型のメッセージを受け入れ、`_Output` 型のメッセージを送信します。 `transformer` クラスは、`single_link_registry` をターゲット ブロックのリンク マネージャーとして指定し、`multi_link_registry` をソース ブロックのリンク マネージャーとして指定します。 したがって、`transformer` オブジェクトで許容されるターゲットは 1 つだけですが、ソースの数に制限はありません。  
  

 派生したクラス`source_block`6 つのメソッドを実装する必要があります: [propagate_to_any_targets](reference/source-block-class.md#propagate_to_any_targets)、 [accept_message](reference/source-block-class.md#accept_message)、 [reserve_message](reference/source-block-class.md#reserve_message)、 [consume_message](reference/source-block-class.md#consume_message)、 [release_message](reference/source-block-class.md#release_message)、および[resume_propagation](reference/source-block-class.md#resume_propagation)です。 派生したクラス`target_block`実装する必要があります、 [propagate_message](reference/propagator-block-class.md#propagate_message)メソッドおよび実装できます必要に応じて、 [send_message](reference/propagator-block-class.md#send_message)メソッドです。 `propagator_block` からの派生は、`source_block` および `target_block` からの派生と機能的には同等です。  


  
 `propagate_to_any_targets` メソッドは、受信メッセージを非同期的または同期的に処理し、送信メッセージを伝達するためにランタイムによって呼び出されます。 `accept_message` メソッドは、メッセージを受け入れるためにターゲット ブロックによって呼び出されます。 `unbounded_buffer` などのメッセージ ブロックの型の多くは、最初にメッセージを受信するターゲットにのみメッセージを送信します。 したがって、メッセージの所有権はそのターゲットに譲渡されます。 などの他のメッセージ ブロック型[concurrency::overwrite_buffer](../../parallel/concrt/reference/overwrite-buffer-class.md)、各ターゲット ブロックにメッセージを提供します。 したがって、`overwrite_buffer` は各ターゲット用にメッセージのコピーを作成します。  
  
 `reserve_message`、`consume_message`、`release_message`、および `resume_propagation` メソッドは、メッセージ ブロックがメッセージの予約に参加できるようにします。 ターゲット ブロックは、提供されたメッセージを予約して後で使用できるようにする場合に、`reserve_message` メソッドを呼び出します。 メッセージを受信したターゲット ブロックは、`consume_message` メソッドを呼び出してそのメッセージを処理するか、`release_message` メソッドを呼び出して予約を取り消すことができます。 `accept_message` メソッドと同様に、`consume_message` の実装では、メッセージの所有権を譲渡するか、メッセージのコピーを返すことができます。 ターゲット ブロックが予約済みのメッセージを処理または解放すると、ランタイムは `resume_propagation` メソッドを呼び出します。 通常、このメソッドは、キュー内の次のメッセージからメッセージ伝達を続行します。  
  
 ランタイムは、`propagate_message` メソッドを呼び出して、別のブロックから現在のブロックにメッセージを非同期的に転送します。 `send_message` メソッドは、非同期的にではなく同期的にメッセージをターゲット ブロックに送信する点を除いて、`propagate_message` と似ています。 `send_message` の既定の実装では、すべての受信メッセージが拒否されます。 ターゲット ブロックに関連付けられているオプションのフィルター関数をメッセージが通過しない場合、ランタイムはどちらのメソッドも呼び出しません。 メッセージ フィルターの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
 [[トップ](#top)]  
  
##  <a name="class"></a> Priority_buffer クラスの定義  
 `priority_buffer` クラスは、受信メッセージを優先順位に従って並べてから、メッセージの受信順に並べるカスタム メッセージ ブロックの型です。 `priority_buffer`クラスに似ています、 [concurrency::unbounded_buffer](reference/unbounded-buffer-class.md)クラス、メッセージのキューを保持しているため、さらにためには、ソースとターゲット メッセージ ブロックの両方として機能し、複数のソースと複数の両方を持つことができますターゲット。 ただし、`unbounded_buffer` でのメッセージの伝達順は、必ずソースからのメッセージの受信順になります。  
  
 `priority_buffer`クラス型のメッセージを受信する std::[組](../../standard-library/tuple-class.md)が含まれている`PriorityType`と`Type`要素。 `PriorityType` は各メッセージの優先順位を保持する型を表し、`Type` はメッセージのデータ部分を表します。 `priority_buffer` クラスは、`Type` 型のメッセージを送信します。 `priority_buffer`クラスは、2 つのメッセージ キューをまた管理: [:priority_queue](../../standard-library/priority-queue-class.md)受信メッセージをオブジェクトおよび std::[キュー](../../standard-library/queue-class.md)送信メッセージのオブジェクト。 `priority_buffer` オブジェクトが複数のメッセージを同時に受信する場合、またはコンシューマーがまだメッセージを読み取っていないときに複数のメッセージを受信する場合、メッセージを優先順位に従って並べ替えると便利です。  
  
 `propagator_block` クラスでは、`priority_buffer` の派生クラスで実装する必要のある 7 つのメソッドに加えて、`link_target_notification` メソッドと `send_message` メソッドもオーバーライドします。 `priority_buffer` クラスでは、2 つのパブリック ヘルパー メソッド (`enqueue` および `dequeue`) と 1 つのプライベート ヘルパー メソッド (`propagate_priority_order`) も定義します。  
  
 次の手順では、`priority_buffer` クラスを実装する方法について説明します。  
  
#### <a name="to-define-the-prioritybuffer-class"></a>priority_buffer クラスを定義するには  
  
1.  C++ ヘッダー ファイルを作成し、名前`priority_buffer.h`です。 または、プロジェクトに含まれる既存のヘッダー ファイルを使用することもできます。  
  
2.  `priority_buffer.h`、次のコードを追加します。  
  
 [!code-cpp[concrt-priority-buffer#1](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_2.h)]  
  
3.  `std`名前空間の特殊化を定義する[std::less](../../standard-library/less-struct.md)と[:greater](../../standard-library/greater-struct.md)同時実行に対して作用する::[メッセージ](../../parallel/concrt/reference/message-class.md)オブジェクト。  
  
 [!code-cpp[concrt-priority-buffer#2](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_3.h)]  
  
     `priority_buffer` クラスは、`message` オブジェクトに `priority_queue` オブジェクトを格納します。 このような型の特殊化によって、優先順位キューでメッセージが優先順位に従って並べ替えられるようになります。 優先順位は、`tuple` オブジェクトの最初の要素です。  
  
4.  `concurrencyex` 名前空間で、`priority_buffer` クラスを宣言します。  
  
 [!code-cpp[concrt-priority-buffer#3](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_4.h)]  
  
     `priority_buffer` クラスは `propagator_block` から派生したものです。 したがって、メッセージを送信することも受信することもできます。 `priority_buffer` クラスは、`Type` 型のメッセージを受信する複数のターゲットを持つことができます。 さらに、`tuple<PriorityType, Type>` 型のメッセージを送信する複数のソースを持つことができます。  
  
5.  `private` クラスの `priority_buffer` セクションに、次のメンバー変数を追加します。  
  
 [!code-cpp[concrt-priority-buffer#6](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_5.h)]  
  
     `priority_queue` オブジェクトは受信メッセージを保持し、`queue` オブジェクトは送信メッセージを保持します。 `priority_buffer` オブジェクトは、複数のメッセージを同時に受信できます。`critical_section` オブジェクトは、入力メッセージのキューへのアクセスを同期します。  
  
6.  `private` セクションで、コピー コンストラクターと代入演算子を定義します。 これにより、`priority_queue` オブジェクトが割り当て可能になるのを防ぎます。  
  
 [!code-cpp[concrt-priority-buffer#7](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_6.h)]  
  
7.  `public` セクションで、多くのメッセージ ブロックの型に共通のコンストラクターを定義します。 デストラクターも定義します。  
  
 [!code-cpp[concrt-priority-buffer#4](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_7.h)]  
  
8.  `public` セクションで、`enqueue` メソッドと `dequeue` メソッドを定義します。 これらのヘルパー メソッドによって、`priority_buffer` オブジェクトとの間でメッセージを送受信する別の手段が提供されます。  
  
 [!code-cpp[concrt-priority-buffer#5](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_8.h)]  
  
9. `protected` セクションで、`propagate_to_any_targets` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#9](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_9.h)]  
  
     `propagate_to_any_targets` メソッドは、入力キューの先頭にあるメッセージを出力キューに転送し、出力キュー内のすべてのメッセージを伝達します。  
  
10. `protected` セクションで、`accept_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#8](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_10.h)]  
  
     ターゲット ブロックから `accept_message` メソッドが呼び出されたとき、`priority_buffer` クラスは、メッセージを最初に受け入れるターゲット ブロックにそのメッセージの所有権を譲渡します  (この動作は `unbounded_buffer` の動作と似ています)。  
  
11. `protected` セクションで、`reserve_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#10](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_11.h)]  
  
     `priority_buffer` クラスは、指定されたメッセージ識別子とキューの先頭にあるメッセージの識別子が一致する場合に、ターゲット ブロックでメッセージを予約できるようにします。 つまり、`priority_buffer` オブジェクトがまだ追加のメッセージを受信しておらず、現在のメッセージも伝達していない場合、ターゲットはメッセージを予約できます。  
  
12. `protected` セクションで、`consume_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#11](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_12.h)]  
  
     ターゲット ブロックは、予約したメッセージの所有権を譲渡するために `consume_message` を呼び出します。  
  
13. `protected` セクションで、`release_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#12](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_13.h)]  
  
     ターゲット ブロックは、メッセージの予約を取り消すために `release_message` を呼び出します。  
  
14. `protected` セクションで、`resume_propagation` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#13](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_14.h)]  
  
     ターゲット ブロックが予約済みのメッセージを処理または解放すると、ランタイムは `resume_propagation` を呼び出します。 このメソッドは、出力キュー内のすべてのメッセージを伝達します。  
  
15. `protected` セクションで、`link_target_notification` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#14](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_15.h)]  
  
     `_M_pReservedFor` メンバー変数は、`source_block` 基底クラスによって定義されます。 このメンバー変数は、出力キューの先頭にあるメッセージの予約を保持しているターゲット ブロック (存在する場合) を指します。 新しいターゲットが `link_target_notification` オブジェクトにリンクされると、ランタイムは `priority_buffer` を呼び出します。 このメソッドは、ターゲットが予約を保持していない場合に、出力キュー内のすべてのメッセージを伝達します。  
  
16. `private` セクションで、`propagate_priority_order` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#15](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_16.h)]  
  
     このメソッドは、出力キュー内のすべてのメッセージを伝達します。 ターゲット ブロックの 1 つがメッセージを受け入れるまで、キュー内の各メッセージが各ターゲット ブロックに提供されます。 `priority_buffer` クラスは、送信メッセージの順序を保持しています。 そこで、このメソッドでは、出力キュー内の最初のメッセージがいずれかのターゲット ブロックによって受け入れられるまで、他のメッセージをターゲット ブロックに提供しないようにします。  
  
17. `protected` セクションで、`propagate_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#16](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_17.h)]  
  
     `propagate_message` メソッドは、`priority_buffer` クラスがメッセージの受信側 (つまりターゲット) として機能するようにします。 このメソッドは、指定されたソース ブロックから提供されたメッセージを受信し、そのメッセージを優先順位キューに挿入します。 その後、`propagate_message` メソッドは、すべての出力メッセージをターゲット ブロックに非同期的に送信します。  
  

     ランタイムが呼び出す場合は、このメソッドを呼び出します、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)関数または他のメッセージ ブロックにメッセージ ブロックを接続するとき。  

  
18. `protected` セクションで、`send_message` メソッドを定義します。  
  
 [!code-cpp[concrt-priority-buffer#17](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_18.h)]  
  
     `send_message` メソッドは `propagate_message` と似ています。 ただし、このメソッドは、非同期的にではなく同期的に出力メッセージを送信します。  
  

     ランタイムが呼び出す場合など、同期送信操作中にこのメソッドを呼び出して、 [concurrency::send](reference/concurrency-namespace-functions.md#send)関数。  
  
 `priority_buffer` クラスには、多くのメッセージ ブロックの型に共通のコンストラクター オーバーロードが含まれています。 一部のコンス トラクターが受け取るオーバー ロード[concurrency::scheduler](../../parallel/concrt/reference/scheduler-class.md)または[concurrency::schedulegroup](../../parallel/concrt/reference/schedulegroup-class.md)オブジェクトで、特定のタスク スケジューラで管理するため、メッセージ ブロックを有効にします。 フィルター関数を受け取るコンストラクター オーバーロードもあります。 フィルター関数を使用すると、メッセージ ブロックでのメッセージの受け入れまたは拒否をメッセージ ペイロードに基づいて行うことができます。 メッセージ フィルターの詳細については、次を参照してください。[非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)です。 タスク スケジューラに関する詳細については、次を参照してください。[タスク スケジューラ](../../parallel/concrt/task-scheduler-concurrency-runtime.md)です。  
  
 `priority_buffer`クラスは、優先度でメッセージを注文し、メッセージが受信される順序、によってこのクラスは、最も役に立つを受信したときのメッセージ、非同期的になどを呼び出すとき、 [concurrency::asend](reference/concurrency-namespace-functions.md#asend)関数または他のメッセージ ブロックにメッセージ ブロックを接続するとき。  
  
 [[トップ](#top)]  
  
##  <a name="complete"></a> 完全な例  
 次の例では、`priority_buffer` クラスの完全な定義を示します。  
  
 [!code-cpp[concrt-priority-buffer#18](../../parallel/concrt/codesnippet/cpp/walkthrough-creating-a-custom-message-block_19.h)]  
  
 次の例は、の数を同時に実行`asend`と[concurrency::receive](reference/concurrency-namespace-functions.md#receive)での操作、`priority_buffer`オブジェクト。  

  
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
 コード例をコピーして、Visual Studio プロジェクトに貼り付けるかの定義を貼り付けます、`priority_buffer`という名前のファイル内のクラス`priority_buffer.h`という名前のファイルで、テスト プログラム`priority_buffer.cpp`し、Visual Studio で、次のコマンドを実行コマンド プロンプト ウィンドウです。  
  
 **cl.exe/EHsc priority_buffer.cpp**  
  
## <a name="see-also"></a>関連項目  
 [同時実行ランタイムのチュートリアル](../../parallel/concrt/concurrency-runtime-walkthroughs.md)   
 [非同期メッセージ ブロック](../../parallel/concrt/asynchronous-message-blocks.md)   
 [メッセージ パッシング関数](../../parallel/concrt/message-passing-functions.md)
