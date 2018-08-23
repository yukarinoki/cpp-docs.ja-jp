---
title: EventSource クラス |Microsoft Docs
ms.custom: ''
ms.date: 03/22/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource
dev_langs:
- C++
helpviewer_keywords:
- EventSource class
ms.assetid: 91f1c072-6af4-44e6-b6d8-ac6d0c688dde
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8805547c5803ae665178330063e6b77b1b3c662e
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/22/2018
ms.locfileid: "42596212"
---
# <a name="eventsource-class"></a>EventSource クラス

非アジャイルのイベントを表します。 **EventSource**メンバー関数を追加、削除、およびイベント ハンドラーを呼び出します。 アジャイルのイベントを使用して[AgileEventSource](agileeventsource-class.md)します。

## <a name="syntax"></a>構文

```cpp
template<typename TDelegateInterface>
class EventSource;
```

### <a name="parameters"></a>パラメーター

*TDelegateInterface*  
イベント ハンドラーを表すデリゲートのインターフェイスです。

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[EventSource::EventSource コンストラクター](../windows/eventsource-eventsource-constructor.md)|新しいインスタンスを初期化、 **EventSource**クラス。|

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[EventSource::Add メソッド](../windows/eventsource-add-method.md)|現在のイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。 **EventSource**オブジェクト。|
|[EventSource::GetSize メソッド](../windows/eventsource-getsize-method.md)|現在関連付けられているイベント ハンドラーの数を取得**EventSource**オブジェクト|
|[EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)|現在関連付けられている各イベント ハンドラーを呼び出す**EventSource**オブジェクトの指定された引数の型と引数を使用します。|
|[EventSource::Remove メソッド](../windows/eventsource-remove-method.md)|現在関連付けられているイベント ハンドラーのセットから、指定されたイベント登録トークンによって表されるイベント ハンドラーを削除します。 **EventSource**オブジェクト。|

### <a name="protected-data-members"></a>プロテクト データ メンバー

|name|説明|
|----------|-----------------|
|[EventSource::addRemoveLock_ データ メンバー](../windows/eventsource-addremovelock-data-member.md)|アクセスを同期、 [targets _](../windows/eventsource-targets-data-member.md)配列を追加するときに、削除、またはイベント ハンドラーを呼び出します。|
|[EventSource::targets_ データ メンバー](../windows/eventsource-targets-data-member.md)|1 つまたは複数のイベント ハンドラーの配列。|
|[EventSource::targetsPointerLock_ データ メンバー](../windows/eventsource-targetspointerlock-data-member.md)|この eventsource イベントのハンドラーが追加されている場合でも、削除、または呼び出される内部データ メンバーへのアクセスを同期します。|

## <a name="inheritance-hierarchy"></a>継承階層

`EventSource`

## <a name="requirements"></a>要件

**ヘッダー:** event.h

**名前空間:** Microsoft::WRL

## <a name="see-also"></a>関連項目

[Microsoft::WRL 名前空間](../windows/microsoft-wrl-namespace.md)  
[AgileEventSource クラス](agileeventsource-class.md)