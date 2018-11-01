---
title: message_processor クラス
ms.date: 11/04/2016
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
ms.openlocfilehash: d6e45613e0b412b6b94dba3c4a435115e32c7d6a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50438221"
---
# <a name="messageprocessor-class"></a>message_processor クラス

`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。 メッセージの順序は保証されません。

## <a name="syntax"></a>構文

```
template<class T>
class message_processor;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージ内のペイロードのデータ型は、これによって処理される`message_processor`オブジェクト。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|型の別名の`T`します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[async_send](#async_send)|派生クラスでオーバーライドされるのブロックに非同期的にメッセージを格納します。|
|[sync_send](#sync_send)|派生クラスでオーバーライドされると、同期的にブロックにメッセージに配置します。|
|[wait](#wait)|派生クラスでオーバーライドされると、すべての非同期操作が完了するまで待機します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|派生クラスでオーバーライドされると、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに 1 回呼び出されます。|

## <a name="inheritance-hierarchy"></a>継承階層

`message_processor`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="async_send"></a> async_send

派生クラスでオーバーライドされるのブロックに非同期的にメッセージを格納します。

```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
A`message`非同期的に送信するオブジェクト。

### <a name="remarks"></a>Remarks

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

##  <a name="process_incoming_message"></a> process_incoming_message

派生クラスでオーバーライドされると、ブロックにメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空にすることが検出するたびに 1 回呼び出されます。

```
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>Remarks

メッセージ ブロックの実装では、このメソッドをオーバーライドする必要があります。

##  <a name="sync_send"></a> sync_send

派生クラスでオーバーライドされると、同期的にブロックにメッセージに配置します。

```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
A`message`同期的に送信するオブジェクト。

### <a name="remarks"></a>Remarks

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

##  <a name="wait"></a> 待機

派生クラスでオーバーライドされると、すべての非同期操作が完了するまで待機します。

```
virtual void wait() = 0;
```

### <a name="remarks"></a>Remarks

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[ordered_message_processor クラス](ordered-message-processor-class.md)
