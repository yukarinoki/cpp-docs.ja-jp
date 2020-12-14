---
description: '詳細情報: message_processor クラス'
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
ms.openlocfilehash: f74314bde6e12ea8b00bfc7bfd2567ca15864f75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202198"
---
# <a name="message_processor-class"></a>message_processor クラス

`message_processor` クラスは、`message` オブジェクトを処理するための抽象基底クラスです。 メッセージの順序は保証されません。

## <a name="syntax"></a>構文

```cpp
template<class T>
class message_processor;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
このオブジェクトによって処理されるメッセージ内のペイロードのデータ型 `message_processor` 。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|の型のエイリアス `T` 。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[async_send](#async_send)|派生クラスでオーバーライドされると、メッセージをブロックに非同期的に配置します。|
|[sync_send](#sync_send)|派生クラスでオーバーライドされると、メッセージをブロックに同期的に配置します。|
|[wait](#wait)|派生クラスでオーバーライドされると、すべての非同期操作が完了するまで待機します。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[process_incoming_message](#process_incoming_message)|派生クラスでオーバーライドされると、ブロックへのメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空であることが見つかるたびに呼び出されます。|

## <a name="inheritance-hierarchy"></a>継承階層

`message_processor`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="async_send"></a><a name="async_send"></a> async_send

派生クラスでオーバーライドされると、メッセージをブロックに非同期的に配置します。

```cpp
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
`message`非同期的に送信するオブジェクト。

### <a name="remarks"></a>解説

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

## <a name="process_incoming_message"></a><a name="process_incoming_message"></a> process_incoming_message

派生クラスでオーバーライドされると、ブロックへのメッセージの転送処理を実行します。 新しいメッセージが追加され、キューが空であることが見つかるたびに呼び出されます。

```cpp
virtual void process_incoming_message() = 0;
```

### <a name="remarks"></a>解説

メッセージブロックの実装では、このメソッドをオーバーライドする必要があります。

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

派生クラスでオーバーライドされると、メッセージをブロックに同期的に配置します。

```cpp
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```

### <a name="parameters"></a>パラメーター

*_Msg*<br/>
`message`同期的に送信するオブジェクト。

### <a name="remarks"></a>解説

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

## <a name="wait"></a><a name="wait"></a> 待機

派生クラスでオーバーライドされると、すべての非同期操作が完了するまで待機します。

```cpp
virtual void wait() = 0;
```

### <a name="remarks"></a>解説

プロセッサの実装では、このメソッドをオーバーライドする必要があります。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[ordered_message_processor クラス](ordered-message-processor-class.md)
