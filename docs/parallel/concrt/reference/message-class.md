---
title: message クラス |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
dev_langs:
- C++
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14fe0fa284a56c45404d8b568acf3b0d360fa27a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2018
ms.locfileid: "33687944"
---
# <a name="message-class"></a>message クラス
メッセージング ブロック間で渡されるデータ ペイロードが格納される、基本的なメッセージ エンベロープ。  
  
## <a name="syntax"></a>構文  
  
```
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 メッセージ内のペイロードのデータ型。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-typedefs"></a>パブリック typedef  
  
|名前|説明|  
|----------|-----------------|  
|`type`|型の別名`T`です。|  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[message](#ctor)|オーバーロードされます。 `message` オブジェクトを構築します。|  
|[~ message デストラクター](#dtor)|`message` オブジェクトを破棄します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[add_ref](#add_ref)|参照カウントに追加、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックのために使用します。|  
|[msg_id](#msg_id)|ID を返します、`message`オブジェクト。|  
|[remove_ref](#remove_ref)|参照カウントから減算し、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックのために使用します。|  
  
### <a name="public-data-members"></a>パブリック データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[ペイロード](#payload)|ペイロード、`message`オブジェクト。|  
  
## <a name="remarks"></a>コメント  
 詳細については、次を参照してください。[非同期メッセージ ブロック](../../../parallel/concrt/asynchronous-message-blocks.md)です。  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `message`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** agents.h  
  
 **名前空間:** concurrency  
  
##  <a name="add_ref"></a> add_ref 

 参照カウントに追加、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックのために使用します。  
  
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
 `_P`  
 このメッセージのペイロード。  
  
 `_Id`  
 このメッセージの一意の ID。  
  
 `_Msg`  
 参照またはへのポインター、`message`オブジェクト。  
  
### <a name="remarks"></a>コメント  
 ポインターを受け取るコンス トラクター、`message`オブジェクト引数のスローされて、 [invalid_argument](../../../standard-library/invalid-argument-class.md)例外場合、パラメーター`_Msg`は`NULL`します。  
  
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

 参照カウントから減算し、`message`オブジェクト。 参照カウントのメッセージの有効期間を決定する必要があるメッセージ ブロックのために使用します。  
  
```
long remove_ref();
```  
  
### <a name="return-value"></a>戻り値  
 参照カウントの新しい値。  
  
## <a name="see-also"></a>関連項目  
 [concurrency 名前空間](concurrency-namespace.md)
