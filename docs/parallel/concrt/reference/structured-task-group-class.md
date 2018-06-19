---
title: structured_task_group クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- structured_task_group
- PPL/concurrency::structured_task_group
- PPL/concurrency::structured_task_group::structured_task_group
- PPL/concurrency::structured_task_group::cancel
- PPL/concurrency::structured_task_group::is_canceling
- PPL/concurrency::structured_task_group::run
- PPL/concurrency::structured_task_group::run_and_wait
- PPL/concurrency::structured_task_group::wait
dev_langs:
- C++
helpviewer_keywords:
- structured_task_group class
ms.assetid: 742afa8c-c7b6-482c-b0ba-04c809927b22
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5cca5d20b89df97e27529d656e9a6553fd8a1820
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694145"
---
# <a name="structuredtaskgroup-class"></a>structured_task_group クラス
`structured_task_group` クラスは、並列処理の高度に構造化されたコレクションを表します。 `structured_task_group` オブジェクトを使用して個々の並列タスクを `task_handle` のキューに配置し、それらのタスクが完了するまで待機するか、実行が完了する前にタスク グループを取り消すことができます。取り消すと、実行が開始されていないタスクはすべて中止されます。  
  
## <a name="syntax"></a>構文  
  
```
class structured_task_group;
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[structured_task_group](#ctor)|オーバーロードされます。 新しい `structured_task_group` オブジェクトを構築します。|  
|[~ structured_task_group デストラクター](#dtor)|`structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さない期待した、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行される場合を除きの結果としてスタック アンワインド例外のためです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|このタスク グループをルートとする作業のサブツリーをキャンセルしようとしています。 最大限の努力をによりします。 タスク グループでスケジュールされているすべてのタスクが取り消さ推移的に可能な場合です。|  
|[is_canceling](#is_canceling)|かどうか、タスク グループは現在、取り消し中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出されました、`structured_task_group`オブジェクト (確かに戻るには、このメソッドを修飾などが`true`)。 大文字と小文字がある可能性がある、`structured_task_group`オブジェクトはインラインで実行し、さらに、タスク グループのツリーで、作業が取り消されました。 キャンセルがこれを経由して流れます前もってを判断できますランタイムこれらの場所などの場合`structured_task_group`オブジェクト、`true`も返されます。|  
|[run](#run)|オーバーロードされます。 タスクがスケジュール、`structured_task_group`オブジェクト。 呼び出し元の有効期間を管理する、`task_handle`に渡されたオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョンで`_Placement`タスクがそのパラメーターで指定された場所で実行する方向にバイアスされます。|  
|[run_and_wait](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでの支援を受けてインラインを実行するタスクをスケジュール、`structured_task_group`完全キャンセルのサポートのオブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。 関数が処理されるまでにし、待機、`structured_task_group`オブジェクトが完了したか取り消されました。|  
|[wait](#wait)|すべての作業になるまで待機します`structured_task_group`が完了したかが取り消されます。|  
  
## <a name="remarks"></a>コメント  
 使用率の重大な制限の数が、`structured_task_group`オブジェクトのパフォーマンスを得るためには。  
  
-   1 つ`structured_task_group`オブジェクトは、複数のスレッドで使用できません。 すべての操作、`structured_task_group`オブジェクトは、オブジェクトを作成したスレッドで行う必要があります。 このルールに 2 つの例外は、メンバー関数は、`cancel`と`is_canceling`です。 オブジェクトは、ラムダ式のキャプチャ リストにできない可能性があり、タスクがキャンセル操作の 1 つを使用していない限り、タスク内で使用します。  
  
-   スケジュールされたすべてのタスク、`structured_task_group`の使用によりオブジェクトがスケジュールされている`task_handle`オブジェクトの有効期間を明示的に管理する必要があります。  
  
-   複数のグループは、絶対に入れ子になった順序でのみ使用可能性があります。 2 つ`structured_task_group`オブジェクトが宣言されている、2 つ目 (内部の 1 つ) を宣言する必要がありますを除く任意のメソッドの前に消滅させるため`cancel`または`is_canceling`が 1 つ目で呼び出される (外側の 1 つ)。 複数を宣言するだけの場合の両方でこの条件に当てはまる`structured_task_group`がキューに格納されたタスクの場合と同様に、同じまたは機能的には入れ子になったスコープ内のオブジェクト、`structured_task_group`を介して、`run`または`run_and_wait`メソッドです。  
  
-   全般的なとは異なり`task_group`クラス、すべての状態、`structured_task_group`クラスが最終版です。 グループにタスクをキューに登録して、待機時間を完了すると、同じグループをもう一度使用可能性があります。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `structured_task_group`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="cancel"></a> キャンセル 

 このタスク グループをルートとする作業のサブツリーをキャンセルしようとしています。 最大限の努力をによりします。 タスク グループでスケジュールされているすべてのタスクが取り消さ推移的に可能な場合です。  
  
```
void cancel();
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)です。  
  
##  <a name="is_canceling"></a> is_canceling 

 かどうか、タスク グループは現在、取り消し中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出されました、`structured_task_group`オブジェクト (確かに戻るには、このメソッドを修飾などが`true`)。 大文字と小文字がある可能性がある、`structured_task_group`オブジェクトはインラインで実行し、さらに、タスク グループのツリーで、作業が取り消されました。 キャンセルがこれを経由して流れます前もってを判断できますランタイムこれらの場所などの場合`structured_task_group`オブジェクト、`true`も返されます。  
  
```
bool is_canceling();
```  
  
### <a name="return-value"></a>戻り値  
 かどうかを示す、`structured_task_group`オブジェクトは、取り消し中 (または直後にあることが保証)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../../../parallel/concrt/exception-handling-in-the-concurrency-runtime.md#cancellation)です。  
  
##  <a name="run"></a> 実行します。 

 タスクがスケジュール、`structured_task_group`オブジェクト。 呼び出し元の有効期間を管理する、`task_handle`に渡されたオブジェクト、`_Task_handle`パラメーター。 パラメーターを受け取るバージョンで`_Placement`タスクがそのパラメーターで指定された場所で実行する方向にバイアスされます。  
  
```
template<class _Function>
void run(
    task_handle<_Function>& _Task_handle);

template<class _Function>
void run(
    task_handle<_Function>& _Task_handle,
    location& _Placement);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスク ハンドルの本体は実行に呼び出される関数オブジェクトの型。  
  
 `_Task_handle`  
 スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは想定されるまで、ライブに引き続き、`wait`または`run_and_wait`このメソッドが呼び出された`structured_task_group`オブジェクト。  
  
 `_Placement`  
 タスクがによって表される場所への参照、`_Task_handle`パラメーターを実行する必要があります。  
  
### <a name="remarks"></a>コメント  
 ランタイムでは、このメソッドに渡す処理関数のコピーを作成します。 このメソッドに渡された関数オブジェクトで発生した状態の変更は、その関数のオブジェクトのコピーには表示されません。  
  
 場合、`structured_task_group`スタック例外からアンワインドの結果として destructs、する必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッドです。 ここでは、デストラクターが適切にキャンセルされタスクによって表されるを待つ、`_Task_handle`パラメーターを完了します。  
  
 スロー、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスク処理する場合に例外によって指定された、`_Task_handle`パラメーターは既にによってタスク グループ オブジェクトにスケジュールされている、`run`メソッドが行われていない中間の呼び出しといずれか、`wait`または`run_and_wait`そのタスク グループのメソッドです。  
  
##  <a name="run_and_wait"></a> run_and_wait 

 呼び出し元のコンテキストでの支援を受けてインラインを実行するタスクをスケジュール、`structured_task_group`完全キャンセルのサポートのオブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。 関数が処理されるまでにし、待機、`structured_task_group`オブジェクトが完了したか取り消されました。  
  
```
template<class _Function>
task_group_status run_and_wait(task_handle<_Function>& _Task_handle);

template<class _Function>
task_group_status run_and_wait(const _Function& _Func);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスクの実行に呼び出される関数オブジェクトの型。  
  
 `_Task_handle`  
 呼び出し元のコンテキストのインラインを実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは、本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。  
  
 `_Func`  
 作業の本体を呼び出すために呼び出される関数。 ラムダ式、またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクトがあります`void operator()()`です。  
  
### <a name="return-value"></a>戻り値  
 待機に条件が満たされたかどうかを示す値、タスク グループが取り消されたため、明示的なキャンセル操作またはのいずれかのタスクからスローされた例外のいずれか。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>コメント  
 その 1 つ以上の次のようにスケジュールされたタスクに注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する場合があります。  
  
 次のようにスケジュールされたタスクの 1 人以上`structured_task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達、`run_and_wait`メソッド。  
  
 この関数から制御が戻た後、`structured_task_group`オブジェクトし、見なされ、最終的な状態では使用できません。 後の使用率に注意してください、`run_and_wait`メソッドを返します未定義の動作が発生します。  
  
 このいずれかのメソッドを呼び出すことを義務付けてがある場合に、例外的ではない実行のパス、または`wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。  
  
##  <a name="ctor"></a> structured_task_group 

 新しい `structured_task_group` オブジェクトを構築します。  
  
```
structured_task_group();

structured_task_group(cancellation_token _CancellationToken);
```  
  
### <a name="parameters"></a>パラメーター  
 `_CancellationToken`  
 この構造化タスク グループに関連付けるキャンセル トークン。 トークンが取り消されたときに、構造化タスク グループが取り消されます。  
  
### <a name="remarks"></a>コメント  
 キャンセル トークンを受け取るコンス トラクターを作成、`structured_task_group`をトークンに関連付けられているソースが取り消されたときに取り消されます。 別のトークンまたはトークンを設定せずに、親グループからの暗黙的な取り消しに参加している場合は、この構造化タスク グループを分離も、明示的なキャンセル トークンを提供します。  
  
##  <a name="dtor"></a> ~structured_task_group 

 `structured_task_group` オブジェクトを破棄します。 いずれかを呼び出さない期待した、`wait`または`run_and_wait`デストラクターの実行前にオブジェクトのメソッド、デストラクターが実行される場合を除きの結果としてスタック アンワインド例外のためです。  
  
```
~structured_task_group();
```  
  
### <a name="remarks"></a>コメント  
 通常の実行 (たとえば、いないスタック アンワインド例外のため) とも、結果として、デストラクターが実行する場合、`wait`も`run_and_wait`メソッドが呼び出されて、デストラクターがスローする可能性があります、 [missing_wait](missing-wait-class.md)例外。  
  
##  <a name="wait"></a> 待機 

 すべての作業になるまで待機します`structured_task_group`が完了したかが取り消されます。  
  
```
task_group_status wait();
```  
  
### <a name="return-value"></a>戻り値  
 待機に条件が満たされたかどうかを示す値、タスク グループが取り消されたため、明示的なキャンセル操作またはのいずれかのタスクからスローされた例外のいずれか。 詳細については、次を参照してください[task_group_status。](concurrency-namespace-enums.md)  
  
### <a name="remarks"></a>コメント  
 その 1 つ以上の次のようにスケジュールされたタスクに注意してください`structured_task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する場合があります。  
  
 次のようにスケジュールされたタスクの 1 人以上`structured_task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達、`wait`メソッド。  
  
 この関数から制御が戻た後、`structured_task_group`オブジェクトし、見なされ、最終的な状態では使用できません。 後の使用率に注意してください、`wait`メソッドを返します未定義の動作が発生します。  
  
 このいずれかのメソッドを呼び出すことを義務付けてがある場合に、例外的ではない実行のパス、または`run_and_wait`メソッドのデストラクターの前に、`structured_task_group`を実行します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [task_group クラス](task-group-class.md)   
 [task_handle クラス](task-handle-class.md)
