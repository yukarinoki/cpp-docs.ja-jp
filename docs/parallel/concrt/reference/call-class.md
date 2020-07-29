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
ms.openlocfilehash: d3dc730e19aaadfed171816e92837ba2766883cb
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213880"
---
# <a name="call-class"></a>call クラス

`call` メッセージング ブロックは、複数のソースを持つ、順序付けられた `target_block` であり、メッセージを受け取ったときに指定された関数を呼び出します。

## <a name="syntax"></a>構文

```cpp
template<class T, class _FunctorType = std::function<void(T const&)>>
class call : public target_block<multi_link_registry<ISource<T>>>;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
このブロックに反映されたメッセージのペイロードの種類。

*_FunctorType*<br/>
このブロックが受け入れることができる関数のシグネチャ。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[call](#ctor)|オーバーロードされます。 `call` メッセージング ブロックを構築します。|
|[~ 呼び出しデストラクター](#dtor)|`call`メッセージングブロックを破棄します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[process_input_messages](#process_input_messages)|入力メッセージに対して call 関数を実行します。|
|[process_message](#process_message)|このメッセージングブロックで受け入れられたメッセージを処理 `call` します。|
|[propagate_message](#propagate_message)|`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `call` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[send_message](#send_message)|`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `call` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。|
|[supports_anonymous_source](#supports_anonymous_source)|このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。 ( [ITarget:: supports_anonymous_source](itarget-class.md#supports_anonymous_source)よりも優先されます)。|

## <a name="remarks"></a>解説

詳細については、「[非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

[ITarget](itarget-class.md)

[target_block](target-block-class.md)

`call`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="call"></a><a name="ctor"></a>発信

`call` メッセージング ブロックを構築します。

```cpp
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
受け入れられた各メッセージに対して呼び出される関数。

*_Filter*<br/>
提供されたメッセージを受け入れるかどうかを決定するフィルター関数。

*_PScheduler*<br/>
その内部で `Scheduler` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。

*_PScheduleGroup*<br/>
その内部で `ScheduleGroup` メッセージング ブロックの反映タスクがスケジュールされる `call` オブジェクト。 使用される `Scheduler` オブジェクトは、スケジュール グループによって暗黙的に指定されます。

### <a name="remarks"></a>解説

`_PScheduler` または `_PScheduleGroup` パラメーターを指定しない場合、ランタイムは既定のスケジューラを使用しています。

この型 `_Call_method` は、 `void (T const &)` `call` メッセージを処理するためにこのメッセージングブロックによって呼び出される、署名付きのファンクタです。

この型は、提供された `filter_method` `bool (T const &)` メッセージを `call` 受け入れるかどうかを判断するために、このメッセージングブロックによって呼び出される、シグネチャを持つファンクタです。

## <a name="call"></a><a name="dtor"></a>~ 呼び出し

`call`メッセージングブロックを破棄します。

```cpp
~call();
```

## <a name="process_input_messages"></a><a name="process_input_messages"></a>process_input_messages

入力メッセージに対して call 関数を実行します。

```cpp
virtual void process_input_messages(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理するメッセージへのポインター。

## <a name="process_message"></a><a name="process_message"></a>process_message

このメッセージングブロックで受け入れられたメッセージを処理 `call` します。

```cpp
virtual void process_message(_Inout_ message<T>* _PMessage);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
処理するメッセージへのポインター。

## <a name="propagate_message"></a><a name="propagate_message"></a>propagate_message

`ISource`ブロックからこのメッセージングブロックに非同期的にメッセージを渡し `call` ます。 これは、 `propagate` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した[message_status](concurrency-namespace-enums.md)を示します。

## <a name="send_message"></a><a name="send_message"></a>send_message

`ISource`ブロックからこのメッセージングブロックにメッセージを同期的に渡し `call` ます。 これは、 `send` ソースブロックによって呼び出されたときに、メソッドによって呼び出されます。

```cpp
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した[message_status](concurrency-namespace-enums.md)を示します。

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a>supports_anonymous_source

このブロックがリンクされて `supports_anonymous_source` いないソースによって提供されるメッセージを受け入れることができることを示すために、メソッドをオーバーライドします。

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**`true`** ブロックは提供されたメッセージを延期しないためです。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[トランスフォーマークラス](transformer-class.md)
