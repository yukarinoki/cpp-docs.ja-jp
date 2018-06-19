---
title: EventSource クラス |Microsoft ドキュメント
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
ms.openlocfilehash: b2d466b317927cd8de259637450b68b6aaf13bd5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876515"
---
# <a name="eventsource-class"></a>EventSource クラス
非アジャイルのイベントを表します。 EventSource メンバー関数は、追加、削除、およびイベント ハンドラーを呼び出します。 アジャイルのイベントを使用して[AgileEventSource](agileeventsource-class.md)です。 
  
## <a name="syntax"></a>構文  
  
```  
template<typename TDelegateInterface>  
class EventSource;  
```  
  
#### <a name="parameters"></a>パラメーター  
 `TDelegateInterface`  
 デリゲートをイベント ハンドラーを表すインターフェイス。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[EventSource::EventSource コンストラクター](../windows/eventsource-eventsource-constructor.md)|EventSource クラスの新しいインスタンスを初期化します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[EventSource::Add メソッド](../windows/eventsource-add-method.md)|現在の EventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。|  
|[EventSource::GetSize メソッド](../windows/eventsource-getsize-method.md)|現在の EventSource オブジェクトに関連付けられているイベント ハンドラーの数を取得します。|  
|[EventSource::InvokeAll メソッド](../windows/eventsource-invokeall-method.md)|指定した引数型と引数を使用して現在の EventSource オブジェクトに関連付けられている各イベント ハンドラーを呼び出します。|  
|[EventSource::Remove メソッド](../windows/eventsource-remove-method.md)|現在の EventSource オブジェクトに関連付けられているイベント ハンドラーのセットから指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。|  
  
### <a name="protected-data-members"></a>プロテクト データ メンバー  
  
|名前|説明|  
|----------|-----------------|  
|[EventSource::addRemoveLock_ データ メンバー](../windows/eventsource-addremovelock-data-member.md)|アクセスを同期化、 [targets _](../windows/eventsource-targets-data-member.md)配列を追加する場合、削除、またはイベント ハンドラーの呼び出しです。|  
|[EventSource::targets_ データ メンバー](../windows/eventsource-targets-data-member.md)|1 つまたは複数のイベント ハンドラーの配列。|  
|[EventSource::targetsPointerLock_ データ メンバー](../windows/eventsource-targetspointerlock-data-member.md)|この EventSource のイベント ハンドラーが追加されている中であっても、削除、または呼び出される内部データ メンバーへのアクセスを同期します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `EventSource`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::wrl Namespace](../windows/microsoft-wrl-namespace.md)
[AgileEventSource クラス](agileeventsource-class.md)