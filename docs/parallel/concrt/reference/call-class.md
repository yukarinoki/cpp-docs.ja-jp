---
title: クラスを呼び出します |。Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 47f72948621e9311f05af74f75d80cd35c1deddc
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
---
# <a name="call-class"></a>call クラス
`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。  
  
## <a name="syntax"></a>構文  
  
```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージのペイロードの型は、このブロックに伝達されます。  
  
 `_FunctorType`  
 このブロックが受け入れることができる関数のシグネチャ。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[call](#ctor)|オーバーロードされます。 構築、`call`メッセージング ブロックです。|  
|[~ call デストラクター](#dtor)|破棄、`call`メッセージング ブロックです。|  
  
### <a name="protected-methods"></a>プロテクト メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[process_input_messages](#process_input_messages)|入力メッセージの関数を呼び出すを実行します。|  
|[process_message](#process_message)|これによって承認されたメッセージを処理`call`メッセージング ブロックです。|  
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`ブロックをこの`call`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`ブロックをこの`call`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。|  
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることができます。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 [ITarget](itarget-class.md)  
  
 [target_block](target-block-class.md)  
  
 `call`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="ctor"></a> 呼び出し 

 構築、`call`メッセージング ブロックです。  
  
```
call(
    _Call_method const& _Func);

call(
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func);

call(
    Scheduler& _PScheduler,
    _Call_method const& _Func,
    filter_method const& _Filter);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func);

call(
    ScheduleGroup& _PScheduleGroup,
    _Call_method const& _Func,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>パラメーター  
 `_Func`  
 許容されるメッセージごとに呼び出される関数。  
  
 `_Filter`  
 提供されたメッセージを受け付けるかどうかを判断するフィルター関数。  
  
 `_PScheduler`  
 その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。  
  
 `_PScheduleGroup`  
 その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。  
  
### <a name="remarks"></a>コメント  
 `_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。  
  
 型`_Call_method`シグネチャを持つファンクターは、`void (T const &)`これは、これによって呼び出されます。`call`メッセージング ブロックでメッセージを処理します。  
  
 型`filter_method`シグネチャを持つファンクターは、`bool (T const &)`これは、これによって呼び出されます。`call`メッセージング ブロックを、提供されたメッセージを受け入れる必要がありますかどうかを判断します。  
  
##  <a name="dtor"></a> ~ を呼び出す 

 破棄、`call`メッセージング ブロックです。  
  
```
~call();
```  
  
##  <a name="process_input_messages"></a> process_input_messages 

 入力メッセージの関数を呼び出すを実行します。  
  
```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
  
##  <a name="process_message"></a> process_message 

 これによって承認されたメッセージを処理`call`メッセージング ブロックです。  
  
```
virtual void process_message(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 処理されるメッセージへのポインター。  
  
##  <a name="propagate_message"></a> propagate_message 

 メッセージを非同期的に渡す、`ISource`ブロックをこの`call`メッセージング ブロックです。 によって呼び出された、`propagate`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
##  <a name="send_message"></a> send_message 

 メッセージを同期的に渡す、`ISource`ブロックをこの`call`メッセージング ブロックです。 によって呼び出された、`send`メソッドは、ソース ブロックによって呼び出されるとします。  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>パラメーター  
 `_PMessage`  
 `message` オブジェクトを指すポインター。  
  
 `_PSource`  
 メッセージを提供する、ソース ブロックへのポインター。  
  
### <a name="return-value"></a>戻り値  
 A [message_status](concurrency-namespace-enums.md)のメッセージを行うには、対象の決定を示す値。  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 上書き、`supports_anonymous_source`を示すこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることができます。  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>戻り値  
 `true` ブロックは延期いないために、メッセージを提供します。  
  
## <a name="see-also"></a>関連項目  
 [同時実行 Namespace](concurrency-namespace.md)   
 [transformer クラス](transformer-class.md)
