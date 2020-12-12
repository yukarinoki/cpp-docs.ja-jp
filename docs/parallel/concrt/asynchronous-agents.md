---
description: 詳細については、「非同期エージェント」を参照してください。
title: 非同期エージェント
ms.date: 11/19/2018
helpviewer_keywords:
- asynchronous agents
- agents [Concurrency Runtime]
ms.assetid: 6cf6ccc6-87f1-4e14-af15-ea8ba58fef1a
ms.openlocfilehash: 38d2325404d83443ed0bd054793ca200a562359f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338288"
---
# <a name="asynchronous-agents"></a>非同期エージェント

*非同期エージェント*(または *エージェント*) は、他のエージェントと非同期に連携して大規模なコンピューティングタスクを解決するアプリケーションコンポーネントです。 エージェントは、ライフサイクルを設定したタスクと考えることができます。 たとえば、1つのエージェントが入力/出力デバイス (キーボード、ディスク上のファイル、ネットワーク接続など) からデータを読み取る場合や、使用可能になったときに別のエージェントがそのデータに対して操作を実行する場合があります。 最初のエージェントは、メッセージパッシングを使用して、より多くのデータが使用可能であることを2番目のエージェントに通知します。 同時実行ランタイムタスクスケジューラは、効率的な優先権を必要とせずに、エージェントが協調的にブロックおよび生成できるようにするための効率的なメカニズムを提供します。

エージェントライブラリは、非同期エージェントを表す [concurrency:: agent](../../parallel/concrt/reference/agent-class.md) クラスを定義します。 `agent` は、仮想メソッド [concurrency:: agent:: run](reference/agent-class.md#run)を宣言する抽象クラスです。 メソッドは、 `run` エージェントによって実行されるタスクを実行します。 は抽象であるため `run` 、から派生するすべてのクラスでこのメソッドを実装する必要があり `agent` ます。

## <a name="agent-life-cycle"></a>エージェントのライフサイクル

エージェントには、ライフサイクルが設定されています。 [Concurrency:: agent_status](reference/concurrency-namespace-enums.md#agent_status)列挙は、エージェントのさまざまな状態を定義します。 次の図は、ある状態から別の状態へのエージェントの進行状況を示す状態図を示しています。 この図では、実線はアプリケーションから呼び出すメソッドを表しています。点線は、ランタイムから呼び出されるメソッドを表します。

![エージェントの状態ダイアグラム](../../parallel/concrt/media/agentstate.png "エージェントの状態ダイアグラム")

次の表では、列挙体の各状態について説明し `agent_status` ます。

|エージェントの状態|説明|
|-----------------|-----------------|
|`agent_created`|エージェントの実行がスケジュールされていません。|
|`agent_runnable`|ランタイムは、エージェントの実行をスケジュールしています。|
|`agent_started`|エージェントが起動し、実行されています。|
|`agent_done`|エージェントが終了しました。|
|`agent_canceled`|エージェントは、状態に入る前に取り消されました `started` 。|

`agent_created` はエージェントの初期状態で、は `agent_runnable` `agent_started` アクティブな状態であり、 `agent_done` とはターミナルの状態 `agent_canceled` です。

オブジェクトの現在の状態を取得するには、 [concurrency:: agent:: status](reference/agent-class.md#status) メソッドを使用し `agent` ます。 メソッドは `status` 同時実行セーフですが、エージェントの状態は、メソッドから制御が戻ったときに変わる可能性が `status` あります。 たとえば、メソッドを呼び出すときにエージェントの状態がになる `agent_started` 場合 `status` がありますが、メソッドが返された直後に状態に移行することができ `agent_done` `status` ます。

## <a name="methods-and-features"></a>メソッドと機能

次の表は、クラスに属する重要なメソッドの一部を示して `agent` います。 クラスのすべてのメソッドの詳細については `agent` 、「 [agent クラス](../../parallel/concrt/reference/agent-class.md)」を参照してください。

|Method|説明|
|------------|-----------------|
|[start](reference/agent-class.md#start)|オブジェクトの `agent` 実行をスケジュールし、状態に設定し `agent_runnable` ます。|
|[実行](reference/agent-class.md#run)|オブジェクトによって実行されるタスクを実行し `agent` ます。|
|[完了](reference/agent-class.md#done)|エージェントを状態に移動 `agent_done` します。|
|[cancel](../../parallel/concrt/cancellation-in-the-ppl.md#cancel)|エージェントが開始されていない場合、このメソッドはエージェントの実行を取り消し、状態に設定し `agent_canceled` ます。|
|[status](reference/agent-class.md#status)|オブジェクトの現在の状態を取得し `agent` ます。|
|[wait](reference/agent-class.md#wait)|オブジェクトが状態または状態になるのを待機 `agent` `agent_done` `agent_canceled` します。|
|[wait_for_all](reference/agent-class.md#wait_for_all)|指定されたすべての `agent` オブジェクトが `agent_done` 状態または状態になるのを待機 `agent_canceled` します。|
|[wait_for_one](reference/agent-class.md#wait_for_one)|指定されたオブジェクトの少なく `agent` とも1つが、または状態になるまで待機 `agent_done` `agent_canceled` します。|

エージェントオブジェクトを作成したら、 [concurrency:: agent:: start](reference/agent-class.md#start) メソッドを呼び出して、実行のスケジュールを設定します。 ランタイムは、 `run` エージェントをスケジュールした後にメソッドを呼び出し、状態に設定し `agent_runnable` ます。

ランタイムは、非同期エージェントによってスローされた例外を管理しません。 例外処理とエージェントの詳細については、「 [例外処理](../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md)」を参照してください。

## <a name="example"></a>例

基本的なエージェントベースのアプリケーションを作成する方法を示す例については、「 [チュートリアル: Agent-Based アプリケーションの作成](../../parallel/concrt/walkthrough-creating-an-agent-based-application.md)」を参照してください。

## <a name="see-also"></a>関連項目

[非同期エージェント ライブラリ](../../parallel/concrt/asynchronous-agents-library.md)
