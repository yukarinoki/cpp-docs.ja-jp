---
title: agent クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- agent
- AGENTS/concurrency::agent
- AGENTS/concurrency::agent::agent
- AGENTS/concurrency::agent::cancel
- AGENTS/concurrency::agent::start
- AGENTS/concurrency::agent::status
- AGENTS/concurrency::agent::status_port
- AGENTS/concurrency::agent::wait
- AGENTS/concurrency::agent::wait_for_all
- AGENTS/concurrency::agent::wait_for_one
- AGENTS/concurrency::agent::done
- AGENTS/concurrency::agent::run
dev_langs:
- C++
helpviewer_keywords:
- agent class
ms.assetid: 1b09e3d2-5e37-4966-b016-907ef1512456
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fbc8542af8073b2cb95517ea39d89258afac633c
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694158"
---
# <a name="agent-class"></a>agent クラス
すべての独立エージェントの基底クラスとして使用されるクラスです。 他のエージェントに状態が表示されないようにしたり、メッセージ渡しでやり取りしたりする目的で使用されます。  
  
## <a name="syntax"></a>構文  
  
```
class agent;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[agent](#ctor)|オーバーロードされます。 エージェントを構築します。|  
|[~ agent デストラクター](#dtor)|エージェントを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|いずれかからのエージェントの移動、`agent_created`または`agent_runnable`状態を`agent_canceled`状態です。|  
|[start](#start)|エージェントに移動、`agent_created`状態、`agent_runnable`状態、および実行をスケジュールします。|  
|[status](#status)|エージェントからのステータス情報の同期ソースです。|  
|[status_port](#status_port)|エージェントからのステータス情報の非同期のソースです。|  
|[wait](#wait)|エージェントのタスクを完了するまで待機します。|  
|[wait_for_all](#wait_for_all)|すべてのタスクの実行に指定されたエージェントを待機します。|  
|[wait_for_one](#wait_for_one)|いずれかの指定されたエージェントのタスクを完了するを待機します。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[done](#done)|エージェントを移動、`agent_done`状態、エージェントが完了したことを示すです。|  
|[run](#run)|エージェントの主なタスクを表します。 `run` 派生クラスでオーバーライドされる必要があり、エージェントで行う必要がありますを指定しますが、開始された後です。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期エージェント](../../../parallel/concrt/asynchronous-agents.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `agent`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> エージェント 

 エージェントを構築します。  
  
```
agent();

agent(Scheduler& _PScheduler);

agent(ScheduleGroup& _PGroup);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PScheduler`  
 `Scheduler`オブジェクト内のエージェントの実行タスクがスケジュールされています。  
  
 `_PGroup`  
 `ScheduleGroup`オブジェクト内のエージェントの実行タスクがスケジュールされています。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 指定しない場合、ランタイムは、既定のスケジューラを使用して、`_PScheduler`または`_PGroup`パラメーター。  
  
##  <a name="dtor"></a> ~ エージェント 

 エージェントを破棄します。  
  
```
virtual ~agent();
```  
  
### <a name="remarks"></a>コメント  
 終了状態に含まれていないエージェントを破棄すると、エラーが (いずれか`agent_done`または`agent_canceled`)。 継承するクラスのデストラクターでのターミナル状態になるまでにエージェントを待機してこれを回避する、`agent`クラスです。  
  
##  <a name="cancel"></a> キャンセル 

 いずれかからのエージェントの移動、`agent_created`または`agent_runnable`状態を`agent_canceled`状態です。  
  
```
bool cancel();
```  
  
### <a name="return-value"></a>戻り値  
 `true` エージェントが取り消された場合`false`それ以外の場合。 既に開始されたか、またはが既に完了した場合、エージェントをキャンセルできません。  
  
##  <a name="done"></a> 完成です 

 エージェントを移動、`agent_done`状態、エージェントが完了したことを示すです。  
  
```
bool done();
```  
  
### <a name="return-value"></a>戻り値  
 `true` エージェントに移動した場合、`agent_done`状態、`false`それ以外の場合。 取り消されたエージェントに移動することはできません、`agent_done`状態です。  
  
### <a name="remarks"></a>コメント  
 最後に、このメソッドを呼び出す必要があります、`run`エージェントの実行がわかっている場合、メソッドが完了します。  
  
##  <a name="run"></a> 実行します。 

 エージェントの主なタスクを表します。 `run` 派生クラスでオーバーライドされる必要があり、エージェントで行う必要がありますを指定しますが、開始された後です。  
  
```
virtual void run() = 0;
```  
  
### <a name="remarks"></a>コメント  
 エージェントの状態が変更された`agent_started`右このメソッドが呼び出される前にします。 メソッドを呼び出す必要があります`done`してエージェントを戻る前に適切な状態にし、例外をスローしないことがあります。  
  
##  <a name="start"></a> 開始 

 エージェントに移動、`agent_created`状態、`agent_runnable`状態、および実行をスケジュールします。  
  
```
bool start();
```  
  
### <a name="return-value"></a>戻り値  
 `true` エージェントが正常に開始された場合`false`それ以外の場合。 取り消されたエージェントを開始できません。  
  
##  <a name="status"></a> 状態 

 エージェントからのステータス情報の同期ソースです。  
  
```
agent_status status();
```  
  
### <a name="return-value"></a>戻り値  
 エージェントの現在の状態を返します。 この返された状態でした返された直後に変更することに注意してください。  
  
##  <a name="status_port"></a> status_port 

 エージェントからのステータス情報の非同期のソースです。  
  
```
ISource<agent_status>* status_port();
```  
  
### <a name="return-value"></a>戻り値  
 エージェントの現在の状態に関するメッセージを送信できるメッセージのソースを返します。  
  
##  <a name="wait"></a> 待機 

 エージェントのタスクを完了するまで待機します。  
  
```
static agent_status __cdecl wait(
    _Inout_ agent* _PAgent,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PAgent`  
 待機するエージェントへのポインター。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="return-value"></a>戻り値  
 `agent_status`待機が完了すると、エージェントのです。 指定できます`agent_canceled`または`agent_done`です。  
  
### <a name="remarks"></a>コメント  
 エージェントが入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間では、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
##  <a name="wait_for_all"></a> wait_for_all 

 すべてのタスクの実行に指定されたエージェントを待機します。  
  
```
static void __cdecl wait_for_all(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    _Out_writes_opt_(count) agent_status* _PStatus = NULL,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 エージェントのポインター、配列内に存在数`_PAgents`です。  
  
 `_PAgents`  
 待機するエージェントへのポインターの配列。  
  
 `_PStatus`  
 エージェントの状態の配列へのポインター。 各状態の値は、メソッドが戻るときに、対応するエージェントの状態を表します。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="remarks"></a>コメント  
 エージェントが入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間では、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
##  <a name="wait_for_one"></a> wait_for_one 

 いずれかの指定されたエージェントのタスクを完了するを待機します。  
  
```
static void __cdecl wait_for_one(
    size_t count,
    _In_reads_(count) agent** _PAgents,
    agent_status& _Status,
    size_t& _Index,
    unsigned int _Timeout = COOPERATIVE_TIMEOUT_INFINITE);
```  
  
### <a name="parameters"></a>パラメーター  
 `count`  
 エージェントのポインター、配列内に存在数`_PAgents`です。  
  
 `_PAgents`  
 待機するエージェントへのポインターの配列。  
  
 `_Status`  
 エージェントの状態を格納する変数への参照。  
  
 `_Index`  
 エージェントのインデックスを格納する変数への参照。  
  
 `_Timeout`  
 ミリ秒単位の待機する最大時間。  
  
### <a name="remarks"></a>コメント  
 エージェントが入ったときに、エージェント タスクが完了した、`agent_canceled`または`agent_done`状態です。  
  
 場合、パラメーター`_Timeout`定数以外の値を持つ`COOPERATIVE_TIMEOUT_INFINITE`、例外[operation_timed_out](operation-timed-out-class.md)が、一定の時間では、エージェントがそのタスクを完了する前に有効期限が切れる場合にスローされます。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
