---
title: call クラス
ms.date: 11/04/2016
f1_keywords:
- call
- AGENTS/concurrency::call
- AGENTS/concurrency::call::call
- AGENTS/concurrency::call::process_input_messages
- AGENTS/concurrency::call::process_message
- AGENTS/concurrency::call::propagate_message
- AGENTS/concurrency::call::send_message
- AGENTS/concurrency::call::supports_anonymous_source
helpviewer_keywords:
- call class
ms.assetid: 1521970a-1e9c-4b0c-a681-d18e40976f49
ms.openlocfilehash: 5164d2787c86e6c909418f353c15c876d1397afe
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50566102"
---
# <a name="call-class"></a>call クラス

`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。

## <a name="syntax"></a>構文

```
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージのペイロードの型は、このブロックに伝達されます。

*_FunctorType*<br/>
このブロックが受け入れることができる関数のシグネチャ。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[call](#ctor)|オーバーロードされます。 `call` メッセージング ブロックを構築します。|
|[~ call デストラクター](#dtor)|破棄、`call`メッセージング ブロックします。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|入力メッセージ呼び出し関数を実行します。|
|[process_message](#process_message)|これによって承認されたメッセージを処理`call`メッセージング ブロックします。|
|[propagate_message](#propagate_message)|メッセージを非同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。|
|[send_message](#send_message)|メッセージを同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。 (上書き[itarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source))。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="ctor"></a> 呼び出し

`call` メッセージング ブロックを構築します。

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

*_Func*<br/>
許容されるメッセージごとに呼び出される関数。

*フィルター (_f)*<br/>
提供されたメッセージを受け入れられる必要があるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>Remarks

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

型`_Call_method`シグネチャを持つ、ファンクターは、`void (T const &)`これによって呼び出される`call`メッセージング ブロックはメッセージを処理します。

型`filter_method`シグネチャを持つ、ファンクターは、`bool (T const &)`これによって呼び出される`call`メッセージング ブロックを提供されたメッセージを受け入れる必要があるかどうかを判断します。

##  <a name="dtor"></a> ~ を呼び出す

破棄、`call`メッセージング ブロックします。

```
~call();
```

##  <a name="process_input_messages"></a> process_input_messages

入力メッセージ呼び出し関数を実行します。

```
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理されるメッセージへのポインター。

##  <a name="process_message"></a> process_message

これによって承認されたメッセージを処理`call`メッセージング ブロックします。

```
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理されるメッセージへのポインター。

##  <a name="propagate_message"></a> propagate_message

メッセージを非同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出されます、`propagate`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="send_message"></a> send_message

メッセージを同期的に渡す、`ISource`このブロック`call`メッセージング ブロックします。 によって呼び出されます、`send`メソッドは、ソース ブロックによって呼び出されます。

```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

上書き、`supports_anonymous_source`メソッドをこのブロックがリンクされていないソースによって提供されたメッセージを受け入れることを示します。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**true**ブロックは延期しないため、メッセージを提供します。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[transformer クラス](transformer-class.md)
