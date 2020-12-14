---
description: '詳細: message クラス'
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
ms.openlocfilehash: 0e15dafd9606e68f7a6ed1bed3795791c0f6870c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202315"
---
# <a name="message-class"></a>message クラス

メッセージング ブロック間で渡されるデータ ペイロードが格納される、基本的なメッセージ エンベロープ。

## <a name="syntax"></a>構文

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>パラメーター

*T*<br/>
メッセージ内のペイロードのデータ型。

## <a name="members"></a>メンバー

### <a name="public-typedefs"></a>パブリック typedef

|名前|説明|
|----------|-----------------|
|`type`|の型のエイリアス `T` 。|

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[message](#ctor)|オーバーロードされます。 `message` オブジェクトを構築します。|
|[~ メッセージデストラクター](#dtor)|`message` オブジェクトを破棄します。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[add_ref](#add_ref)|オブジェクトの参照カウントにを追加し `message` ます。 メッセージの有効期間を決定するために参照カウントを必要とするメッセージブロックに使用されます。|
|[msg_id](#msg_id)|オブジェクトの ID を返し `message` ます。|
|[remove_ref](#remove_ref)|オブジェクトの参照カウントから減算し `message` ます。 メッセージの有効期間を決定するために参照カウントを必要とするメッセージブロックに使用されます。|

### <a name="public-data-members"></a>パブリック データ メンバー

|名前|説明|
|----------|-----------------|
|[payload](#payload)|オブジェクトのペイロード `message` 。|

## <a name="remarks"></a>解説

詳細については、「 [非同期メッセージブロック](../../../parallel/concrt/asynchronous-message-blocks.md)」を参照してください。

## <a name="inheritance-hierarchy"></a>継承階層

`message`

## <a name="requirements"></a>要件

**ヘッダー:** agents.h

**名前空間:** concurrency

## <a name="add_ref"></a><a name="add_ref"></a> add_ref

オブジェクトの参照カウントにを追加し `message` ます。 メッセージの有効期間を決定するために参照カウントを必要とするメッセージブロックに使用されます。

```cpp
long add_ref();
```

### <a name="return-value"></a>戻り値

参照カウントの新しい値。

## <a name="message"></a><a name="ctor"></a> メッセージ

`message` オブジェクトを構築します。

```cpp
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
オブジェクトへの参照またはポインター `message` 。

### <a name="remarks"></a>解説

オブジェクトへのポインターを `message` 引数として受け取るコンストラクターは、パラメーターがの場合に [invalid_argument](../../../standard-library/invalid-argument-class.md) の例外をスローし `_Msg` `NULL` ます。

## <a name="message"></a><a name="dtor"></a> ~ メッセージ

`message` オブジェクトを破棄します。

```cpp
virtual ~message();
```

## <a name="msg_id"></a><a name="msg_id"></a> msg_id

オブジェクトの ID を返し `message` ます。

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>戻り値

`runtime_object_identity` オブジェクトの `message` です。

## <a name="payload"></a><a name="payload"></a> ペイ

オブジェクトのペイロード `message` 。

```cpp
T const payload;
```

## <a name="remove_ref"></a><a name="remove_ref"></a> remove_ref

オブジェクトの参照カウントから減算し `message` ます。 メッセージの有効期間を決定するために参照カウントを必要とするメッセージブロックに使用されます。

```cpp
long remove_ref();
```

### <a name="return-value"></a>戻り値

参照カウントの新しい値。

## <a name="see-also"></a>関連項目

[concurrency 名前空間](concurrency-namespace.md)
