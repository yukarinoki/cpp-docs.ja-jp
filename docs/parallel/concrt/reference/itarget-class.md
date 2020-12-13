---
description: '詳細情報: ITarget クラス'
title: ITarget クラス
ms.date: 11/04/2016
f1_keywords:
- ITarget
- AGENTS/concurrency::ITarget
- AGENTS/concurrency::ITarget::propagate
- AGENTS/concurrency::ITarget::send
- AGENTS/concurrency::ITarget::supports_anonymous_source
- AGENTS/concurrency::ITarget::link_source
- AGENTS/concurrency::ITarget::unlink_source
- AGENTS/concurrency::ITarget::unlink_sources
helpviewer_keywords:
- ITarget class
ms.assetid: 5678db25-112a-4f72-be13-42e16b67c48b
ms.openlocfilehash: 6a1e900fa67ac5ee72305f18679e7a0fc38a2386
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334400"
---
# <a name="itarget-class"></a>ITarget クラス

`ITarget` クラスは、すべてのターゲット ブロックのインターフェイスです。 ターゲット ブロックは、`ISource` ブロックから提供されたメッセージを処理します。

## <a name="syntax"></a>構文

```cpp
template<class T>
class ITarget;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
ターゲットブロックによって受け入れられるメッセージ内のペイロードのデータ型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`filter_method`|提供された **`bool`** メッセージを受け入れる必要があるかどうかを判断するために値を返す、ブロックによって使用されるメソッドのシグネチャ。|
|`type`|の型のエイリアス `T` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ ITarget デストラクター](#dtor)|`ITarget` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[伝](#propagate)|派生クラスでオーバーライドされると、ソースブロックからこのターゲットブロックにメッセージを非同期的に渡します。|
|[送信](#send)|派生クラスでオーバーライドされると、ターゲットブロックにメッセージを同期的に渡します。|
|[supports_anonymous_source](#supports_anonymous_source)|派生クラスでオーバーライドされると、リンクされていないソースによって提供されるメッセージをメッセージブロックが受け入れるかどうかに応じて、true または false を返します。 オーバーライドされたメソッドがを返す場合、 **`true`** 提供されたメッセージをターゲットが延期することはできません。延期されたメッセージを後で使用する場合は、ソースリンクレジストリでソースを識別する必要があります。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[link_source](#link_source)|派生クラスでオーバーライドされると、指定したソースブロックをこのブロックにリンクし `ITarget` ます。|
|[unlink_source](#unlink_source)|派生クラスでオーバーライドされると、指定したソースブロックをこのブロックからリンク解除し `ITarget` ます。|
|[unlink_sources](#unlink_sources)|派生クラスでオーバーライドされた場合、このブロックのすべてのソースブロックのリンクを解除し `ITarget` ます。|

## <a name="remarks"></a>解説

詳細については、「 [非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`ITarget`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="itarget"></a><a name="dtor"></a> ~ ITarget

`ITarget` オブジェクトを破棄します。

```cpp
virtual ~ITarget();
```

## <a name="link_source"></a><a name="link_source"></a> link_source

派生クラスでオーバーライドされると、指定したソースブロックをこのブロックにリンクし `ITarget` ます。

```cpp
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
`ISource`このブロックにリンクされているブロック `ITarget` 。

### <a name="remarks"></a>解説

この関数は、ブロックで直接呼び出すことはできません `ITarget` 。 ブロックは、 `link_target` `ISource` 対応するターゲットに対してメソッドを呼び出すブロックに対して、メソッドを使用して一緒に接続する必要があり `link_source` ます。

## <a name="propagate"></a><a name="propagate"></a> 伝

派生クラスでオーバーライドされると、ソースブロックからこのターゲットブロックにメッセージを非同期的に渡します。

```cpp
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

### <a name="remarks"></a>解説

パラメーターまたはパラメーターのいずれかがの場合、メソッドは [invalid_argument](../../../standard-library/invalid-argument-class.md) 例外をスローし `_PMessage` `_PSource` `NULL` ます。

## <a name="send"></a><a name="send"></a> 送信

派生クラスでオーバーライドされると、ターゲットブロックにメッセージを同期的に渡します。

```cpp
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソースブロックへのポインター。

### <a name="return-value"></a>戻り値

対象がメッセージに対して実行することを決定した [message_status](concurrency-namespace-enums.md) を示します。

### <a name="remarks"></a>解説

パラメーターまたはパラメーターのいずれかがの場合、メソッドは [invalid_argument](../../../standard-library/invalid-argument-class.md) 例外をスローし `_PMessage` `_PSource` `NULL` ます。

`send`メッセージの開始時以外にメソッドを使用し、ネットワーク内でメッセージを伝達することは危険であり、デッドロックにつながる可能性があります。

`send`がを返した場合、メッセージは既に受け入れられていて、ターゲットブロックに転送されているか、ターゲットによって拒否されています。

## <a name="supports_anonymous_source"></a><a name="supports_anonymous_source"></a> supports_anonymous_source

派生クラスでオーバーライドされると、リンクされていないソースによって提供されるメッセージをメッセージブロックが受け入れるかどうかに応じて、true または false を返します。 オーバーライドされたメソッドがを返す場合、 **`true`** 提供されたメッセージをターゲットが延期することはできません。延期されたメッセージを後で使用する場合は、ソースが sourse リンクレジストリで識別される必要があります。

```cpp
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**`true`** ブロックがリンクされていないソースからのメッセージを受け入れることができる場合は **`false`** 。それ以外の場合は。

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

派生クラスでオーバーライドされると、指定したソースブロックをこのブロックからリンク解除し `ITarget` ます。

```cpp
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
`ISource`このブロックからリンク解除されているブロック `ITarget` 。

### <a name="remarks"></a>解説

この関数は、ブロックで直接呼び出すことはできません `ITarget` 。 ブロックは、ブロックでメソッドまたはメソッドを使用して切断する必要があり `unlink_target` `unlink_targets` `ISource` ます。これにより、 `unlink_source` 対応するターゲットでメソッドが呼び出されます。

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

派生クラスでオーバーライドされた場合、このブロックのすべてのソースブロックのリンクを解除し `ITarget` ます。

```cpp
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)<br/>
[ISource クラス](isource-class.md)
