---
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
ms.openlocfilehash: 59a0f66a0ba3b10c3307a835ff6ccaa216596538
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339541"
---
# <a name="itarget-class"></a>ITarget クラス

`ITarget` クラスは、すべてのターゲット ブロックのインターフェイスです。 ターゲット ブロックは、`ISource` ブロックから提供されたメッセージを処理します。

## <a name="syntax"></a>構文

```
template<class T>
class ITarget;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージ内のペイロードのデータ型は、ターゲット ブロックによって受け入れられます。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`filter_method`|返すブロックで使用されるメソッドのシグネチャを`bool`提供されたメッセージを受け入れられる必要があるかどうかを決定する値。|
|`type`|型の別名の`T`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[~ ITarget デストラクター](#dtor)|`ITarget` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[伝達](#propagate)|派生クラスでオーバーライドされると、非同期的にメッセージをソース ブロックからこのターゲット ブロックに渡します。|
|[send](#send)|派生クラスでオーバーライドされると、ターゲット ブロックにメッセージを同期的に渡します。|
|[supports_anonymous_source](#supports_anonymous_source)|派生クラスでオーバーライドされると、true またはメッセージ ブロックがそれにリンクされていないソースによって提供されるメッセージを受け入れるかどうかによっては false を返します。 オーバーライドされたメソッドが返された場合**true**ターゲットは提供されたメッセージを延期できないように後で、延期されたメッセージの消費量には、そのソース リンクのレジストリに識別するソースが必要です。|

### <a name="protected-methods"></a>プロテクト メソッド

|名前|説明|
|----------|-----------------|
|[link_source](#link_source)|派生クラスでオーバーライドされると、この指定されたソース ブロックをリンク`ITarget`ブロックします。|
|[unlink_source](#unlink_source)|派生クラスでオーバーライドされると、これから指定されたソース ブロックのリンクを解除`ITarget`ブロックします。|
|[unlink_sources](#unlink_sources)|派生クラスでオーバーライドされると、これからのすべてのソース ブロックのリンクを解除`ITarget`ブロックします。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`ITarget`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="dtor"></a> ~ ITarget

`ITarget` オブジェクトを破棄します。

```
virtual ~ITarget();
```

##  <a name="link_source"></a> link_source

派生クラスでオーバーライドされると、この指定されたソース ブロックをリンク`ITarget`ブロックします。

```
virtual void link_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
`ISource`ブロックにリンクされている`ITarget`ブロックします。

### <a name="remarks"></a>Remarks

この関数は、上で直接呼び出されませんが、`ITarget`ブロックします。 使用してブロックを接続する必要があります、`link_target`メソッド`ISource`呼び出しは、ブロック、`link_source`メソッドを対応するターゲット。

##  <a name="propagate"></a> 伝達

派生クラスでオーバーライドされると、非同期的にメッセージをソース ブロックからこのターゲット ブロックに渡します。

```
virtual message_status propagate(
    _Inout_opt_ message<T>* _PMessage,
    _Inout_opt_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

##  <a name="send"></a> 送信

派生クラスでオーバーライドされると、ターゲット ブロックにメッセージを同期的に渡します。

```
virtual message_status send(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PMessage*<br/>
`message` オブジェクトを指すポインター。

*_PSource*<br/>
メッセージを提供するソース ブロックへのポインター。

### <a name="return-value"></a>戻り値

A [message_status](concurrency-namespace-enums.md)メッセージとは、ターゲットの決定を示す値。

### <a name="remarks"></a>Remarks

メソッドはスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)いずれかの例外、`_PMessage`または`_PSource`パラメーターが`NULL`します。

使用して、`send`外部メッセージの開始に使用し、ネットワーク内のメッセージを伝達するメソッドが危険であり、デッドロックが発生する可能性があります。

ときに`send`返します、メッセージが、既にされて受け入れられると、し、ターゲット ブロックに転送またはターゲットが拒否されました。

##  <a name="supports_anonymous_source"></a> supports_anonymous_source

派生クラスでオーバーライドされると、true またはメッセージ ブロックがそれにリンクされていないソースによって提供されるメッセージを受け入れるかどうかによっては false を返します。 オーバーライドされたメソッドが返された場合**true**ターゲットは提供されたメッセージを延期できないように後で、延期されたメッセージの消費量には、そのソース リンクのレジストリに識別するソースが必要です。

```
virtual bool supports_anonymous_source();
```

### <a name="return-value"></a>戻り値

**true**ブロックにリンクされていないソースからのメッセージを受け入れることができる場合**false**それ以外の場合。

##  <a name="unlink_source"></a> unlink_source

派生クラスでオーバーライドされると、これから指定されたソース ブロックのリンクを解除`ITarget`ブロックします。

```
virtual void unlink_source(_Inout_ ISource<T>* _PSource) = 0;
```

### <a name="parameters"></a>パラメーター

*_PSource*<br/>
`ISource`こちらのリンクが解除されるブロック`ITarget`ブロックします。

### <a name="remarks"></a>Remarks

この関数は、上で直接呼び出されませんが、`ITarget`ブロックします。 使用してブロックを切断する必要があります、`unlink_target`または`unlink_targets`メソッド`ISource`呼び出しは、ブロック、`unlink_source`メソッドを対応するターゲット。

##  <a name="unlink_sources"></a> unlink_sources

派生クラスでオーバーライドされると、これからのすべてのソース ブロックのリンクを解除`ITarget`ブロックします。

```
virtual void unlink_sources() = 0;
```

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)<br/>
[ISource クラス](isource-class.md)
