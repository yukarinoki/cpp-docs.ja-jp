---
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
ms.openlocfilehash: 5b0704f3d666eca08bafb33f9236709478d347d8
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301878"
---
# <a name="isource-class"></a>ISource クラス

`ISource` クラスは、すべてのソース ブロック用のインターフェイスです。 ソース ブロックは、メッセージを `ITarget` ブロックに伝達します。

## <a name="syntax"></a>構文

```
template<class T>
class ISource;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
ソース ブロックによって生成されるメッセージ内のペイロードのデータ型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`source_type`|型の別名の`T`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ ISource デストラクター](#dtor)|`ISource` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[accept](#accept)|派生クラスでオーバーライドされると、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を転送します。|
|[acquire_ref](#acquire_ref)|派生クラスでオーバーライドされると、この参照カウントを取得`ISource`ブロックを削除しないようにします。|
|[使用します。](#consume)|派生クラスでオーバーライドされると、これによって以前に提供されたメッセージを使用して`ISource`をブロックし、呼び出し元に所有権を譲渡する、ターゲットが正常に予約されています。|
|[link_target](#link_target)|派生クラスでオーバーライドされると、このターゲット ブロックをリンク`ISource`ブロックします。|
|[release](#release)|派生クラスでオーバーライドされると、以前に成功したメッセージの予約を解放します。|
|[release_ref](#release_ref)|派生クラスでオーバーライドされると、この参照カウントを解放`ISource`ブロックします。|
|[reserve](#reserve)|派生クラスでオーバーライドされると、これによって以前に提供されたメッセージを予約`ISource`ブロックします。|
|[unlink_target](#unlink_target)|派生クラスでオーバーライドされると、これからのターゲット ブロックのリンクを解除`ISource`場合、ブロックをリンクできる以前が見つかりました。|
|[unlink_targets](#unlink_targets)|派生クラスでオーバーライドされると、これからのすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`ISource`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="accept"></a> そのまま使用します。

派生クラスでオーバーライドされると、これによって提供されたメッセージを受け入れる`ISource`ブロック、呼び出し元に所有権を転送します。

```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`accept`メソッド。

### <a name="return-value"></a>戻り値

呼び出し元が現在の所有権を持つメッセージへのポインター。

### <a name="remarks"></a>Remarks

`accept`メソッドは、このメッセージが提供されていますが、ターゲットによって呼び出されます`ISource`ブロックします。 渡されたものと異なる場合があります、メッセージ ポインターが返される、`propagate`のメソッド、`ITarget`このソースがメッセージのコピーを作成する場合、ブロックします。

##  <a name="acquire_ref"></a> acquire_ref

派生クラスでオーバーライドされると、この参照カウントを取得`ISource`ブロックを削除しないようにします。

```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出してターゲット ブロックへのポインター。

### <a name="remarks"></a>Remarks

このメソッドを呼び出して、`ITarget`中にこのソースにリンクされているオブジェクト、`link_target`メソッド。

##  <a name="consume"></a> 使用します。

派生クラスでオーバーライドされると、これによって以前に提供されたメッセージを使用して`ISource`をブロックし、呼び出し元に所有権を譲渡する、ターゲットが正常に予約されています。

```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、予約済みの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`consume`メソッド。

### <a name="return-value"></a>戻り値

ポインター、`message`呼び出し元は、の所有権を今すぐにオブジェクトします。

### <a name="remarks"></a>Remarks

`consume`メソッドは`accept`への呼び出しでは前に必ず必要がありますが、`reserve`返さ**true**します。

##  <a name="dtor"></a> ~ISource

`ISource` オブジェクトを破棄します。

```
virtual ~ISource();
```

##  <a name="link_target"></a> link_target

派生クラスでオーバーライドされると、このターゲット ブロックをリンク`ISource`ブロックします。

```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
これにリンクされているターゲット ブロックへのポインター`ISource`ブロックします。

##  <a name="release"></a> リリース

派生クラスでオーバーライドされると、以前に成功したメッセージの予約を解放します。

```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、予約済みの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`release`メソッド。

##  <a name="release_ref"></a> release_ref

派生クラスでオーバーライドされると、この参照カウントを解放`ISource`ブロックします。

```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このメソッドを呼び出してターゲット ブロックへのポインター。

### <a name="remarks"></a>Remarks

このメソッドを呼び出して、`ITarget`このソースからリンクが解除されるオブジェクト。 ソース ブロックは、ターゲット ブロック用に予約されたリソースを解放できます。

##  <a name="reserve"></a> 予約

派生クラスでオーバーライドされると、これによって以前に提供されたメッセージを予約`ISource`ブロックします。

```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_MsgId*<br/>
`runtime_object_identity` 、提供されたの`message`オブジェクト。

*_PTarget*<br/>
呼び出すターゲット ブロックへのポインター、`reserve`メソッド。

### <a name="return-value"></a>戻り値

**true**場合は、メッセージが正常に予約された、 **false**それ以外の場合。 予約はなど、多くの理由で失敗します。 メッセージが既に予約またはソースでした、予約を拒否する、など別のターゲットによって受け入れします。

### <a name="remarks"></a>Remarks

呼び出した後`reserve`、成功した場合、いずれかを呼び出す必要があります`consume`または`release`または所有している、メッセージをそれぞれ付与するためにします。

##  <a name="unlink_target"></a> unlink_target

派生クラスでオーバーライドされると、これからのターゲット ブロックのリンクを解除`ISource`場合、ブロックをリンクできる以前が見つかりました。

```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```

### <a name="parameters"></a>パラメーター

*_PTarget*<br/>
このリンクが解除されるターゲット ブロックへのポインター`ISource`ブロックします。

##  <a name="unlink_targets"></a> unlink_targets

派生クラスでオーバーライドされると、これからのすべてのターゲット ブロックのリンクを解除`ISource`ブロックします。

```
virtual void unlink_targets() = 0;
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[ITarget クラス](itarget-class.md)
