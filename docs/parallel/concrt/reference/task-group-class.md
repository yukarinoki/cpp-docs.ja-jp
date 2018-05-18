`task_group` クラスは、待機または取り消しができる並列処理のコレクションを表します。  
  
## <a name="syntax"></a>構文  
  
```  
class task_group;  
```  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task_group](#ctor)|オーバーロードされます。 新しい `task_group` オブジェクトを構築します。|  
|[~ task_group デストラクター](#dtor)|`task_group` オブジェクトを破棄します。 いずれかを呼び出している必要が、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタックの例外のためのアンワインドの結果として実行する場合を除き、オブジェクトのメソッドです。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[キャンセル](#cancel)|このタスク グループをルートとする作業のサブツリーをキャンセルしようとしています。 最大限の努力をによりします。 タスク グループでスケジュールされているすべてのタスクが取り消さ推移的に可能な場合です。|  
|[is_canceling](#is_canceling)|かどうか、タスク グループは現在、取り消し中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出されました、`task_group`オブジェクト (確かに戻るには、このメソッドを修飾などが`true`)。 大文字と小文字がある可能性がある、`task_group`オブジェクトはインラインで実行し、さらに、タスク グループのツリーで、作業が取り消されました。 キャンセルがこれを経由して流れます前もってを判断できますランタイムこれらの場所などの場合`task_group`オブジェクト、`true`も返されます。|  
|[run](#run)|オーバーロードされます。 タスクがスケジュール、`task_group`オブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。 バージョンをでパラメーターは、可能性のあるランタイム内でヒープ割り当て関数のオブジェクトへの参照を受け取るメソッドへの参照を受け取るバージョンで使用するよりも適切に機能を実行する、`task_handle`オブジェクト。 パラメーターを使用するバージョン`_Placement`タスクがそのパラメーターで指定された場所で実行する方向にバイアスされます。|  
|[run_and_wait](#run_and_wait)|オーバーロードされます。 呼び出し元のコンテキストでの支援を受けてインラインを実行するタスクをスケジュール、`task_group`完全キャンセルのサポートのオブジェクト。 関数が処理されるまでにし、待機、`task_group`オブジェクトが完了したか取り消されました。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。|  
|[wait](#wait)|すべての作業になるまで待機します`task_group`オブジェクトが完了したか取り消されました。|  
  
## <a name="remarks"></a>コメント  
 頻度の高い制限とは異なり`structured_task_group`クラス、`task_group`クラスより一般的な構成要素。 によって説明されている制限のない[structured_task_group](structured-task-group-class.md)です。 `task_group` オブジェクトをスレッド間で使用される安全かつ自由形式の方法で使用される可能性があります。 欠点は、`task_group`コンストラクトでは行うことがありますいないだけでなく`structured_task_group`の少量の作業を実行するタスクを作成します。  
  
 詳細については、次を参照してください。[タスクの並列化](../task-parallelism-concurrency-runtime.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task_group`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppl.h  
  
 **名前空間:** concurrency  
  
##  <a name="cancel"></a> キャンセル 

 このタスク グループをルートとする作業のサブツリーをキャンセルしようとしています。 最大限の努力をによりします。 タスク グループでスケジュールされているすべてのタスクが取り消さ推移的に可能な場合です。  
  
```  
void cancel();  
```  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)です。  
  
##  <a name="is_canceling"></a> is_canceling 

 かどうか、タスク グループは現在、取り消し中、呼び出し元に通知します。 これは必ずしもを`cancel`でメソッドが呼び出されました、`task_group`オブジェクト (確かに戻るには、このメソッドを修飾などが`true`)。 大文字と小文字がある可能性がある、`task_group`オブジェクトはインラインで実行し、さらに、タスク グループのツリーで、作業が取り消されました。 キャンセルがこれを経由して流れます前もってを判断できますランタイムこれらの場所などの場合`task_group`オブジェクト、`true`も返されます。  
  
```  
bool is_canceling();  
```  
  
### <a name="return-value"></a>戻り値  
 かどうかを示す、`task_group`オブジェクトは、取り消し中 (または直後にあることが保証)。  
  
### <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[キャンセル](../cancellation-in-the-ppl.md)です。  
  
##  <a name="run"></a> 実行します。 

 タスクがスケジュール、`task_group`オブジェクト。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。 バージョンをでパラメーターは、可能性のあるランタイム内でヒープ割り当て関数のオブジェクトへの参照を受け取るメソッドへの参照を受け取るバージョンで使用するよりも適切に機能を実行する、`task_handle`オブジェクト。 パラメーターを使用するバージョン`_Placement`タスクがそのパラメーターで指定された場所で実行する方向にバイアスされます。  
  
```  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func  
);  
  
template<  
   typename _Function  
>  
void run(  
   const _Function& _Func,  
   location& _Placement  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   typename _Function  
>  
void run(  
   task_handle<_Function>& _Task_handle,  
   location& _Placement  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 タスク ハンドルの本体は実行に呼び出される関数オブジェクトの型。  
  
 `_Func`  
 タスクの本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`です。  
  
 `_Placement`  
 タスクがによって表される場所への参照、`_Func`パラメーターを実行する必要があります。  
  
 `_Task_handle`  
 スケジュールされている作業へのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは想定されるまで、ライブに引き続き、`wait`または`run_and_wait`このメソッドが呼び出された`task_group`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 ランタイムは、後で、呼び出し元の関数が返された後にとりますを実行する指定された処理関数をスケジュールします。 このメソッドを使用して、 [task_handle](task-handle-class.md)指定された処理関数のコピーを保持するオブジェクト。 そのため、このメソッドに渡された関数オブジェクトで発生した状態の変更は、その関数のオブジェクトのコピーには表示されません。 さらに、作業関数が戻るまで、ポインター、または作業関数への参照によって渡された任意のオブジェクトの有効期間が有効なままことを確認します。  
  
 場合、`task_group`スタック例外からアンワインドの結果として destructs、する必要はありません、呼び出しが行われたいずれかにことを保証するために、`wait`または`run_and_wait`メソッドです。 ここでは、デストラクターが適切にキャンセルされタスクによって表されるを待つ、`_Task_handle`パラメーターを完了します。  
  
 メソッドをスロー、 [invalid_multiple_scheduling](invalid-multiple-scheduling-class.md)タスク処理する場合に例外によって指定された、`_Task_handle`パラメーターは既にによってタスク グループ オブジェクトにスケジュールされている、`run`メソッドがあったとなし介在するを呼び出すいずれかに、`wait`または`run_and_wait`そのタスク グループのメソッドです。  
  
##  <a name="run_and_wait"></a> run_and_wait 

 呼び出し元のコンテキストでの支援を受けてインラインを実行するタスクをスケジュール、`task_group`完全キャンセルのサポートのオブジェクト。 関数が処理されるまでにし、待機、`task_group`オブジェクトが完了したか取り消されました。 場合、`task_handle`オブジェクトがパラメーターとして渡される`run_and_wait`の有効期間を管理するため、呼び出し元が、`task_handle`オブジェクト。  
  
```  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   task_handle<_Function>& _Task_handle  
);  
  
template<  
   class _Function  
>  
task_group_status run_and_wait(  
   const _Function& _Func  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 呼び出され、タスクの本体の実行が関数オブジェクトの型。  
  
 `_Task_handle`  
 呼び出し元のコンテキストのインラインを実行するタスクへのハンドル。 呼び出し元がこのオブジェクトの有効期間の責任に注意してください。 ランタイムは、本来はまで、引き続き、`run_and_wait`メソッドが実行を終了します。  
  
 `_Func`  
 作業の本体を呼び出すために呼び出される関数。 これは、ラムダ式またはシグネチャを持つ関数呼び出し演算子のバージョンをサポートするその他のオブジェクト`void operator()()`です。  
  
### <a name="return-value"></a>戻り値  
 待機に条件が満たされたかどうかを示す値、タスク グループが取り消されたため、明示的なキャンセル操作またはのいずれかのタスクからスローされた例外のいずれか。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)です。  

  
### <a name="remarks"></a>コメント  
 その 1 つ以上の次のようにスケジュールされたタスクに注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する場合があります。  
  
 次のようにスケジュールされたタスクの 1 人以上`task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達、`run_and_wait`メソッド。  
  
 戻ったとき、`run_and_wait`メソッドを`task_group`オブジェクトをランタイムに再利用することができます、クリーンな状態にしたオブジェクトをリセットします。 これにより、大文字と小文字が含まれます。 ここで、`task_group`オブジェクトは取り消されました。  
  
 このいずれかのメソッドを呼び出すことを義務付けてがある場合に、例外的ではない実行のパス、または`wait`メソッドのデストラクターの前に、`task_group`を実行します。  
  
##  <a name="ctor"></a> task_group 

 新しい `task_group` オブジェクトを構築します。  
  
```  
task_group();  
  
task_group(  
   cancellation_token _CancellationToken  
);  
```  
  
### <a name="parameters"></a>パラメーター  
 `_CancellationToken`  
 このタスク グループに関連付けるキャンセル トークン。 トークンが取り消されたときに、タスク グループが取り消されます。  
  
### <a name="remarks"></a>コメント  
 キャンセル トークンを受け取るコンス トラクターを作成、`task_group`をトークンに関連付けられているソースが取り消されたときに取り消されます。 別のトークンまたはトークンを設定せずに、親グループからの暗黙的な取り消しに参加している場合は、このタスク グループを分離も、明示的なキャンセル トークンを提供します。  
  
##  <a name="dtor"></a> ~ task_group 

 `task_group` オブジェクトを破棄します。 いずれかを呼び出している必要が、`wait`または`run_and_wait`実行する前に、デストラクター、デストラクターがスタックの例外のためのアンワインドの結果として実行する場合を除き、オブジェクトのメソッドです。  
  
```  
~task_group();  
```  
  
### <a name="remarks"></a>コメント  
 通常の実行 (たとえば、いないスタック アンワインド例外のため) とも、結果として、デストラクターが実行する場合、`wait`も`run_and_wait`メソッドが呼び出されて、デストラクターがスローする可能性があります、 [missing_wait](missing-wait-class.md)例外。  
  
##  <a name="wait"></a> 待機 

 すべての作業になるまで待機します`task_group`オブジェクトが完了したか取り消されました。  
  
```  
task_group_status wait();  
```  
  
### <a name="return-value"></a>戻り値  
 待機に条件が満たされたかどうかを示す値、タスク グループが取り消されたため、明示的なキャンセル操作またはのいずれかのタスクからスローされた例外のいずれか。 詳細については、次を参照してください。 [task_group_status](concurrency-namespace-enums.md#task_group_status)です。  

  
### <a name="remarks"></a>コメント  
 その 1 つ以上の次のようにスケジュールされたタスクに注意してください`task_group`オブジェクトは呼び出し元のコンテキストのインラインを実行する場合があります。  
  
 次のようにスケジュールされたタスクの 1 人以上`task_group`オブジェクトが例外をスロー、ランタイムは、選択した場合のような例外が 1 つを選択しへの呼び出しから伝達、`wait`メソッド。  
  
 呼び出す`wait`上、`task_group`オブジェクトは、ここで、再利用できるクリーンな状態にリセットします。 これにより、大文字と小文字が含まれます。 ここで、`task_group`オブジェクトは取り消されました。  
  
 このいずれかのメソッドを呼び出すことを義務付けてがある場合に、例外的ではない実行のパス、または`run_and_wait`メソッドのデストラクターの前に、`task_group`を実行します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [structured_task_group クラス](structured-task-group-class.md)   
 [task_handle クラス](task-handle-class.md)