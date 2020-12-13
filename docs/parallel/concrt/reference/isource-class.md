---
description: ': ISource クラスに関する詳細情報'
title: ISource クラス
ms.date: 11/04/2016
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
ms.openlocfilehash: 86a55c9ca056c0aebb98e00c12518293b316bcb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334443"
---
# <a name="isource-class"></a>ISource クラス

`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。 ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。

## <a name="syntax"></a>構文

```cpp
template<class T>
class ISource;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ソースブロックによって生成されるメッセージ内のペイロードのデータ型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`source_type`|の型のエイリアス `T` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ ISource デストラクター](#dtor)|`ISource` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[受入](#accept)|派生クラスでオーバーライドされると、このブロックによって提供されたメッセージを受け取り、 `ISource` 所有権を呼び出し元に譲渡します。|
|[acquire_ref](#acquire_ref)|派生クラスでオーバーライドされると、削除を防ぐために、このブロックの参照カウントを取得し `ISource` ます。|
|[可能性](#consume)|派生クラスでオーバーライドされると、このブロックによって既に提供され、ターゲットによって正常に予約されたメッセージを使用して、 `ISource` 所有権を呼び出し元に譲渡します。|
|[link_target](#link_target)|派生クラスでオーバーライドされると、ターゲットブロックをこのブロックにリンクし `ISource` ます。|
|[解除](#release)|派生クラスでオーバーライドされると、前回成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|派生クラスでオーバーライドされると、このブロックの参照カウントを解放し `ISource` ます。|
|[予約](#reserve)|派生クラスでオーバーライドされると、このブロックによって以前に提供されたメッセージを予約 `ISource` します。|
|[unlink_target](#unlink_target)|派生クラスでオーバーライドされた場合、前にリンクされたターゲットブロックをこのブロックからリンク解除 `ISource` します。|
|[unlink_targets](#unlink_targets)|派生クラスでオーバーライドされた場合、このブロックのすべてのターゲットブロックのリンクを解除し `ISource` ます。|

## <a name="remarks"></a>解説

詳細については、「 [非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`ISource`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="accept"></a><a name="accept"></a> 受入

派生クラスでオーバーライドされると、このブロックによって提供されたメッセージを受け取り、 `ISource` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `accept` 。

### <a name="return-value"></a>戻り値

現在呼び出し元に所有権があることを示すメッセージへのポインター。

### <a name="remarks"></a>解説

メソッドは、 `accept` このブロックによってメッセージが提供されている間、ターゲットによって呼び出され `ISource` ます。 `propagate` `ITarget` このソースがメッセージのコピーを作成することにした場合、返されるメッセージポインターは、ブロックのメソッドに渡されたものと異なる場合があります。

## <a name="acquire_ref"></a><a name="acquire_ref"></a> acquire_ref

派生クラスでオーバーライドされると、削除を防ぐために、このブロックの参照カウントを取得し `ISource` ます。

```cpp
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは `ITarget` 、メソッドの実行中にこのソースにリンクされるオブジェクトによって呼び出され `link_target` ます。

## <a name="consume"></a><a name="consume"></a> 可能性

派生クラスでオーバーライドされると、このブロックによって既に提供され、ターゲットによって正常に予約されたメッセージを使用して、 `ISource` 所有権を呼び出し元に譲渡します。

```cpp
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
予約された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `consume` 。

### <a name="return-value"></a>戻り値

`message`呼び出し元が所有権を持っているオブジェクトへのポインター。

### <a name="remarks"></a>解説

`consume`メソッドはと似ていますが、常にを呼び出した後に、 `accept` 返されたを呼び出す必要があり `reserve` **`true`** ます。

## <a name="isource"></a><a name="dtor"></a> ~ ISource

`ISource` オブジェクトを破棄します。

```cpp
virtual ~ISource();
```

## <a name="link_target"></a><a name="link_target"></a> link_target

派生クラスでオーバーライドされると、ターゲットブロックをこのブロックにリンクし `ISource` ます。

```cpp
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このブロックにリンクされているターゲットブロックへのポインター `ISource` 。

## <a name="release"></a><a name="release"></a> 解除

派生クラスでオーバーライドされると、前回成功したメッセージの予約を解放します。

```cpp
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
予約された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `release` 。

## <a name="release_ref"></a><a name="release_ref"></a> release_ref

派生クラスでオーバーライドされると、このブロックの参照カウントを解放し `ISource` ます。

```cpp
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出しているターゲットブロックへのポインター。

### <a name="remarks"></a>解説

このメソッドは、このソースからリンク解除されているオブジェクトによって呼び出され `ITarget` ます。 ソースブロックは、ターゲットブロック用に予約されているすべてのリソースを解放できます。

## <a name="reserve"></a><a name="reserve"></a> 省

派生クラスでオーバーライドされると、このブロックによって以前に提供されたメッセージを予約 `ISource` します。

```cpp
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
提供された `runtime_object_identity` `message` オブジェクトの。

*_PTarget*<br/>
メソッドを呼び出しているターゲットブロックへのポインター `reserve` 。

### <a name="return-value"></a>戻り値

**`true`** メッセージが正常に予約された場合は **`false`** 。それ以外の場合は。 予約は、さまざまな理由で失敗する可能性があります。これには、メッセージが既に別のターゲットによって既に予約または受け入れられている場合、ソースが予約を拒否する場合などがあります。

### <a name="remarks"></a>解説

を呼び出した後、成功した場合は、 `reserve` `consume` メッセージを `release` 取得または取得するために、またはのいずれかを呼び出す必要があります。

## <a name="unlink_target"></a><a name="unlink_target"></a> unlink_target

派生クラスでオーバーライドされた場合、前にリンクされたターゲットブロックをこのブロックからリンク解除 `ISource` します。

```cpp
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このブロックからリンク解除されているターゲットブロックへのポインター `ISource` 。

## <a name="unlink_targets"></a><a name="unlink_targets"></a> unlink_targets

派生クラスでオーバーライドされた場合、このブロックのすべてのターゲットブロックのリンクを解除し `ISource` ます。

```cpp
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[ITarget クラス](itarget-class.md)
