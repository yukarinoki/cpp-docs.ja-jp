---
title: message クラス
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 83cfdb5807581f7092709691a1839052abdd657c
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/24/2019
ms.locfileid: "64343849"
---
# <a name="message-class"></a>message クラス

メッセージング ブロック間で渡されるデータ ペイロードが格納される、基本的なメッセージ エンベロープ。

## <a name="syntax"></a>構文

```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージ内のペイロードのデータ型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|型の別名の`T`します。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[message](#ctor)|オーバーロードされます。 `message` オブジェクトを構築します。|
|[~ message デストラクター](#dtor)|`message` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add_ref](#add_ref)|参照カウントに追加、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックに使用されます。|
|[msg_id](#msg_id)|ID を返します、`message`オブジェクト。|
|[remove_ref](#remove_ref)|参照カウントから減算し、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックに使用されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[ペイロード](#payload)|ペイロード、`message`オブジェクト。|

## <a name="remarks"></a>Remarks

詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)します。

## <a name="inheritance-hierarchy"></a>継承階層

`message`

## <a name="requirements"></a>必要条件

**ヘッダー:** agents.h

**名前空間:** concurrency

##  <a name="add_ref"></a> add_ref

参照カウントに追加、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックに使用されます。

```
long add_ref();
```

### <a name="return-value"></a>戻り値

参照カウントの新しい値。

##  <a name="ctor"></a> メッセージ

`message` オブジェクトを構築します。

```
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>パラメーター

*_P*<br/>
このメッセージのペイロード。

*_Id*<br/>
このメッセージの一意の ID。

*_Msg*<br/>
ポインターまたは参照を`message`オブジェクト。

### <a name="remarks"></a>Remarks

ポインターを受け取るコンス トラクター、`message`オブジェクト引数のスロー、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合パラメーター`_Msg`は`NULL`。

##  <a name="dtor"></a> ~ メッセージ

`message` オブジェクトを破棄します。

```
virtual ~message();
```

##  <a name="msg_id"></a> msg_id

ID を返します、`message`オブジェクト。

```
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>戻り値

`runtime_object_identity`の`message`オブジェクト。

##  <a name="payload"></a> ペイロード

ペイロード、`message`オブジェクト。

```
T const payload;
```

##  <a name="remove_ref"></a> remove_ref

参照カウントから減算し、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックに使用されます。

```
long remove_ref();
```

### <a name="return-value"></a>戻り値

参照カウントの新しい値。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
