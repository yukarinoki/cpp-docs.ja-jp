---
title: 非同期エージェント |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8649ebe0451e4352b27989563a1a0918afcb5a01
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687980"
---
# <a name="asynchronous-agents"></a>非同期エージェント
*非同期エージェント*(または単*エージェント*) より大きなコンピューティング タスクを解決するには、他のエージェントで非同期的に動作するアプリケーション コンポーネントです。 エージェントの一定のライフ サイクルのあるタスクとして考えます。 たとえば、1 つのエージェントでは、入力/出力デバイス (キーボード、ディスク上のファイル、ネットワーク接続など) と別のエージェントからのデータは、利用可能になったに、そのデータの操作を実行可能性がありますを読み取って可能性があります。 最初のエージェントより多くのデータが使用できることを 2 つ目のエージェントに通知するために、メッセージ パッシングを使用します。 同時実行ランタイムのタスク スケジューラは、ブロッキングや譲渡を協調的にエージェントを有効にする効率的なメカニズムを提供せず、プリエンプションの効率が低下します。  
  

 エージェント ライブラリ、定義、 [concurrency::agent](../../parallel/concrt/reference/agent-class.md)非同期エージェントを表すクラス。 `agent` 仮想メソッドを宣言する抽象クラスは、 [concurrency::agent::run](reference/agent-class.md#run)です。 `run`メソッドは、エージェントによって実行されるタスクを実行します。 `run`は抽象クラスである必要がありますメソッドを実装するこのから派生したすべてのクラスで`agent`です。  
  
## <a name="agent-life-cycle"></a>エージェントのライフ サイクル  
 エージェントでは、一定のライフ サイクルがあります。 [Concurrency::agent_status](reference/concurrency-namespace-enums.md#agent_status)列挙型のエージェントのさまざまな状態を定義します。 次の図は、1 つの状態から別のエージェントの進捗を示す状態図です。 この図では、実線はアプリケーションから呼び出すメソッドを表します。点線は、ランタイムから呼び出されるメソッドを表します。  
  
 ![エージェントの状態ダイアグラム](../../parallel/concrt/media/agentstate.png "agentstate")  
  
 次の表に、各状態の`agent_status`列挙します。  
  
|エージェントの状態|説明|  
|-----------------|-----------------|  
|`agent_created`|実行のため、エージェントがスケジュールされていません。|  
|`agent_runnable`|ランタイムのエージェントの実行スケジュールを設定します。|  
|`agent_started`|エージェントが開始されが実行されています。|  
|`agent_done`|エージェントが完了しました。|  
|`agent_canceled`|入る前に、エージェントが取り消されました、`started`状態です。|  
  
 `agent_created` エージェントの初期状態は、`agent_runnable`と`agent_started`、アクティブな状態と`agent_done`と`agent_canceled`ターミナル状態を示します。  
  
 使用して、 [concurrency::agent::status](reference/agent-class.md#status)の現在の状態を取得する方法を`agent`オブジェクト。 ただし、`status`メソッドは同時実行セーフでは、時間によって、エージェントの状態を変更することができます、`status`メソッドを返します。 たとえば、エージェントの可能性があります、`agent_started`を呼び出すときの状態、`status`メソッドに移動、`agent_done`直後の状態、`status`メソッドを返します。  

  
## <a name="methods-and-features"></a>メソッドと機能  
 次の表はいくつかの重要なメソッドに属している、`agent`クラスです。 すべての詳細については、`agent`クラスのメソッドを参照してください[エージェント クラス](../../parallel/concrt/reference/agent-class.md)です。  
  
|メソッド|説明|  
|------------|-----------------|  
|[start](reference/agent-class.md#start)|スケジュール、`agent`実行のためのオブジェクト設定し、`agent_runnable`状態です。|  
|[run](reference/agent-class.md#run)|によって実行されるタスクを実行、`agent`オブジェクト。|  
|[done](reference/agent-class.md#done)|エージェントに移動、`agent_done`状態です。|  
|[キャンセル](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|エージェントが開始されない場合、このメソッドは、エージェントの実行をキャンセルし設定、`agent_canceled`状態です。|  
|[status](reference/agent-class.md#status)|現在の状態を取得、`agent`オブジェクト。|  
|[wait](reference/agent-class.md#wait)|待機、`agent`を入力するオブジェクト、`agent_done`または`agent_canceled`状態です。|  
|[wait_for_all](reference/agent-class.md#wait_for_all)|指定されたすべての待機`agent`を入力するオブジェクト、`agent_done`または`agent_canceled`状態です。|  
|[wait_for_one](reference/agent-class.md#wait_for_one)|少なくとも 1 つ提供されているを待って`agent`を入力するオブジェクト、`agent_done`または`agent_canceled`状態です。|  
  
 エージェント オブジェクトを作成した後、 [concurrency::agent::start](reference/agent-class.md#start)メソッドの実行スケジュールを設定します。 ランタイムが呼び出す、`run`メソッド設定し、エージェントのスケジュールを設定した後、`agent_runnable`状態です。  
  
 ランタイムは、非同期エージェントによってスローされる例外を管理しません。 例外処理、およびエージェントの詳細については、次を参照してください。[例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)です。  
  
## <a name="example"></a>例  
 例については、基本的なエージェント ベースのアプリケーションを作成する方法を示す、次を参照してください。[チュートリアル: エージェント ベースのアプリケーションを作成する](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)です。  
  
## <a name="see-also"></a>関連項目  
 [非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)

