---
title: task クラス (同時実行ランタイム) |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task
- PPLTASKS/concurrency::task
- PPLTASKS/concurrency::task::task
- PPLTASKS/concurrency::task::get
- PPLTASKS/concurrency::task::is_apartment_aware
- PPLTASKS/concurrency::task::is_done
- PPLTASKS/concurrency::task::scheduler
- PPLTASKS/concurrency::task::then
- PPLTASKS/concurrency::task::wait
dev_langs:
- C++
helpviewer_keywords:
- task class
ms.assetid: cdc3a8c0-5cbe-45a0-b5d5-e9f81d94df1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5887350d9ccdf6fc4a41d72ae8a70fa38d939390
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33694096"
---
# <a name="task-class-concurrency-runtime"></a>task クラス (同時実行ランタイム)
並列パターン ライブラリ (PPL) `task` クラス。 `task` オブジェクトは、非同期的に、他のタスクと同時に実行できる処理、および同時実行ランタイムの並列アルゴリズムによって生成される並列処理を表します。 正常に終了した場合は、型 `_ResultType` の結果が生成されます。 型 `task<void>` のタスクでは結果が作成されません。 タスクは、他のタスクと関係なく待機および取り消しできます。 継続を使用して他のタスクと共に構成することもできます ( `then`)、および結合 ( `when_all`) と choice ( `when_any`) パターン。  
  
## <a name="syntax"></a>構文  
  
```
template <typename T>
class task;

template <>
class task<void>;

template<typename _ReturnType>
class task;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 `T`  
 `_ReturnType`  
 このタスクの結果の型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`result_type`|このクラスのオブジェクトによって生成される結果の型。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[task](#ctor)|オーバーロードされます。 `task` オブジェクトを構築します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[get](#get)|オーバーロードされます。 このタスクによって生成された結果を返します。 タスクが終了状態にない場合、`get` への呼び出しは、そのタスクが完了するまで待機します。 このメソッドは、`result_type` が `void` に指定されたタスクで呼び出された場合は値を返しません。|  
|[is_apartment_aware](#is_apartment_aware)|タスクが Windows ランタイム `IAsyncInfo` インターフェイスをラップ解除するか、こうしたタスクの子であるかを決定します。|  
|[is_done](#is_done)|タスクが完了したかどうかを決定します。|  
|[scheduler](#scheduler)|このタスクのスケジューラを返します|  
|[そうしたら](#then)|オーバーロードされます。 継続タスクをこのタスクに追加します。|  
|[wait](#wait)|このタスクが終了状態になるまで待機します。 タスクの依存関係すべてが満たされ、バックグラウンド ワーカーによって実行用にまだ検出されていない場合、`wait` はタスクをインラインで実行できます。|  
  
### <a name="public-operators"></a>パブリック演算子  
  
|名前|説明|  
|----------|-----------------|  
|[operator!=](#operator_neq)|オーバーロードされます。 2 つの `task` オブジェクトが異なる内部タスクを表すかどうかを決定します。|  
|[operator=](#operator_eq)|オーバーロードされます。 ある `task` オブジェクトの内容を別のオブジェクトの内容で置き換えます。|  
|[operator==](#operator_eq_eq)|オーバーロードされます。 2 つの `task` オブジェクトが同じ内部タスクを表すかどうかを決定します。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `task`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** ppltasks.h  
  
 **名前空間:** concurrency  
  
##  <a name="get"></a> 取得 

 このタスクによって生成された結果を返します。 タスクが終了状態にない場合、`get` への呼び出しは、そのタスクが完了するまで待機します。 このメソッドは、`result_type` が `void` に指定されたタスクで呼び出された場合は値を返しません。  
  
```
_ReturnType get() const;

void get() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクの結果。  
  
### <a name="remarks"></a>コメント  
 タスクが取り消された場合に呼び出し`get`がスローされます、 [task_canceled](task-canceled-class.md)例外。 タスクで別の例外が発生したり、継続元タスクからこのタスクに例外が反映された場合、`get` の呼び出しは、その例外をスローします。  
  
> [!IMPORTANT]
>  ユニバーサル Windows プラットフォーム (UWP) アプリで呼び出すことはありません[concurrency::task::wait](#wait)または`get`(`wait`呼び出し`get`) STA で実行されるコードで それ以外の場合、ランタイム[concurrency::invalid_operation](invalid-operation-class.md)のため、これらのメソッドは、現在のスレッドをブロックし、アプリが応答しなくなる可能性があります。 ただし、結果は直ちに使用できるため、タスク ベースの継続で継続元タスクの結果を受け取るために `get` メソッドを呼び出すことができます。  
  
##  <a name="is_apartment_aware"></a> is_apartment_aware 

 タスクが Windows ランタイム `IAsyncInfo` インターフェイスをラップ解除するか、こうしたタスクの子であるかを決定します。  
  
```
bool is_apartment_aware() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクが `true` インターフェイスをラップ解除するか、こうしたタスクの子である場合は `IAsyncInfo` を返します。それ以外の場合は、`false` を返します。  
  
##  <a name="is_done"></a>  task::is_done メソッド (同時実行ランタイム)  
 タスクが完了したかどうかを決定します。  
  
```
bool is_done() const;
```  
  
### <a name="return-value"></a>戻り値  
 タスクが完了した場合は true を返します。それ以外の場合は false を返します。  
  
### <a name="remarks"></a>コメント  
 関数は、タスクが完了した場合または取り消された場合に true を返します (ユーザー例外の有無は問いません)。  
  
##  <a name="operator_neq"></a> operator!= 

 2 つの `task` オブジェクトが異なる内部タスクを表すかどうかを決定します。  
  
```
bool operator!= (const task<_ReturnType>& _Rhs) const;

bool operator!= (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが異なる基本タスクを参照する場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="operator_eq"></a> 演算子 = 

 ある `task` オブジェクトの内容を別のオブジェクトの内容で置き換えます。  
  
```
task& operator= (const task& _Other);

task& operator= (task&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Other`  
 ソース `task` オブジェクト。  
  
### <a name="return-value"></a>戻り値  
  
### <a name="remarks"></a>コメント  
 `task` がスマート ポインターのように動作すると、コピーの代入の後では、この `task` オブジェクトは `_Other` が実行する実際のタスクと同じタスクを表します。  
  
##  <a name="operator_eq_eq"></a> 演算子 = = 

 2 つの `task` オブジェクトが同じ内部タスクを表すかどうかを決定します。  
  
```
bool operator== (const task<_ReturnType>& _Rhs) const;

bool operator== (const task<void>& _Rhs) const;
```  
  
### <a name="parameters"></a>パラメーター  
 `_Rhs`  
  
### <a name="return-value"></a>戻り値  
 オブジェクトが同じ基本タスクを参照する場合は `true` を返します。それ以外の場合は `false` を返します。  
  
##  <a name="scheduler"></a>  task::scheduler メソッド (同時実行ランタイム)  
 このタスクのスケジューラを返します  
  
```
scheduler_ptr scheduler() const;
```  
  
### <a name="return-value"></a>戻り値  
 スケジューラへのポインター  
  
##  <a name="ctor"></a> タスク 

 `task` オブジェクトを構築します。  
  
```
task();

template<typename T>
__declspec(
    noinline) explicit task(T _Param);

template<typename T>
__declspec(
    noinline) explicit task(T _Param, const task_options& _TaskOptions);

task(
    const task& _Other);

task(
    task&& _Other);
```  
  
### <a name="parameters"></a>パラメーター  
 `T`  
 パラメーターの型。これに基づいてタスクが構築されます。  
  
 `_Param`  
 パラメーター。これに基づいてタスクが構築されます。 これは、ラムダ、関数オブジェクト、`task_completion_event<result_type>`オブジェクト、または Windows ランタイム アプリでタスクを使用している場合、:iasyncinfo です。 ラムダまたは関数オブジェクトと同じ型である必要があります`std::function<X(void)>`X が型の変数を指定できます、 `result_type`、 `task<result_type>`、または Windows ランタイム アプリで:iasyncinfo です。  
  
 `_TaskOptions`  
 タスク オプションには、キャンセル トークン、スケジューラなどがあります。  
  
 `_Other`  
 ソース `task` オブジェクト。  
  
### <a name="remarks"></a>コメント  
 `task` の既定のコンストラクターは、タスクをコンテナー内で使用できるようにすることのみを目的としています。 構築された既定のタスクは、有効なタスクを割り当てるまで使用できません。 などのメソッド`get`、`wait`または`then`がスローされます、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外構築された既定のタスクで呼び出されるとします。  
  
 `task_completion_event` から作成されたタスクは、タスクの完了イベントが設定されたときに完了します (その後で継続がスケジュールされます)。  
  
 キャンセル トークンを使用するバージョンのコンストラクターは、トークンの取得元となる `cancellation_token_source` を使用して取り消すことができるタスクを作成します。 キャンセル トークンを使用せずに作成されたタスクは、取り消すことはできません。  
  
 `Windows::Foundation::IAsyncInfo` インターフェイスまたは `IAsyncInfo` インターフェイスを返すラムダから作成されたタスクは、取り込まれている Windows ランタイムの非同期操作または非同期アクションが完了すると、終了状態になります。 同様に、`task<result_type>` を返すラムダから作成されたタスクは、内側のタスクが終了状態になったとき (ラムダがその状態を返すときではありません)、終了状態になります。  
  
 `task` は、スマート ポインターのように動作し、安全に値渡しされます。 この task には、複数のスレッドからアクセスできます。ロックする必要はありません。  
  
 :Foundation::iasyncinfo インターフェイスまたはそのようなインターフェイスを返すラムダを取るコンス トラクター オーバー ロードでは、Windows ランタイム アプリで利用できますのみです。  
  
 詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
##  <a name="then"></a> そうしたら 

 継続タスクをこのタスクに追加します。  
  
```
template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    _ReturnType>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    const task_options& _TaskOptions = task_options()) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;

template<typename _Function>
__declspec(
    noinline) auto then(const _Function& _Func,
    cancellation_token _CancellationToken,
    task_continuation_context _ContinuationContext) const -> typename details::_ContinuationTypeTraits<_Function,
    void>::_TaskOfType;
```   
  
### <a name="parameters"></a>パラメーター  
 `_Function`  
 このタスクによって呼び出される関数オブジェクトの型。  
  
 `_Func`  
 このタスクが完了したときに実行される継続関数。 この継続関数では、`result_type` または `task<result_type>` の変数を入力として使用する必要があります。`result_type` は、このタスクによって生成される結果の型です。  
  
 `_TaskOptions`  
 タスク オプションには、キャンセル トークン、スケジューラ、および継続コンテキストなどがあります。 既定では、これら 3 つのオプションは継続元タスクから継承されます。  
  
 `_CancellationToken`  
 継続タスクに関連付けるキャンセル トークン。 キャンセル トークンなしで作成された継続タスクは、その継続元タスクのトークンを継承します。  
  
 `_ContinuationContext`  
 継続を実行する状況を指定する変数。 この変数は、UWP アプリで使用すると便利ではのみです。 詳細については、次を参照してください[task_continuation_context。](task-continuation-context-class.md)  
  
### <a name="return-value"></a>戻り値  
 新しく作成された継続タスク。 返されるタスクの結果の型は、`_Func` が返す値によって決まります。  
  
### <a name="remarks"></a>コメント  
 オーバー ロード`then`ラムダまたはファンクタを返す::iasyncinfo インターフェイスを Windows ランタイム アプリに限られます。  
  
 継続タスクを使用して、非同期操作を作成する方法の詳細については、次を参照してください。[タスクの並列化](../../../parallel/concrt/task-parallelism-concurrency-runtime.md)です。  
  
##  <a name="wait"></a> 待機 

 このタスクが終了状態になるまで待機します。 タスクの依存関係すべてが満たされ、バックグラウンド ワーカーによって実行用にまだ検出されていない場合、`wait` はタスクをインラインで実行できます。  
  
```
task_status wait() const;
```  
  
### <a name="return-value"></a>戻り値  
 `task_status` の値。`completed` または `canceled` に設定される可能性があります。 タスクの実行時に例外が発生したり、継続元タスクからこのタスクに例外が反映された場合、`wait` はその例外をスローします。  
  
### <a name="remarks"></a>コメント  
  
> [!IMPORTANT]
>  ユニバーサル Windows プラットフォーム (UWP) アプリで呼び出すことはありません`wait`STA で実行されるコードで それ以外の場合、ランタイム[concurrency::invalid_operation](invalid-operation-class.md)のため、このメソッドは、現在のスレッドをブロックし、アプリが応答しなくなる可能性があります。 ただし、呼び出すことができます、 [concurrency:](#get)タスク ベースの継続で継続元タスクの結果を受信するメソッド。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
