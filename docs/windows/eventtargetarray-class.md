---
title: EventTargetArray クラス |Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2757589509e4a2b091c5057ef2065866a8829494
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570422"
---
# <a name="eventtargetarray-class"></a>EventTargetArray クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Remarks  
 イベント ハンドラーの配列を表します。  
  
 関連付けられているイベント ハンドラー、 [EventSource](../windows/eventsource-class.md)オブジェクトが格納されている保護されたで**EventTargetArray**データ メンバー。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray コンストラクター](../windows/eventtargetarray-eventtargetarray-constructor.md)|新しいインスタンスを初期化、 **EventTargetArray**クラス。|  
|[EventTargetArray::~EventTargetArray デストラクター](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|現在の初期化を解除**EventTargetArray**クラス。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[EventTargetArray::AddTail メソッド](../windows/eventtargetarray-addtail-method.md)|イベント ハンドラーの内部配列の末尾には、指定したイベント ハンドラーを追加します。|  
|[EventTargetArray::Begin メソッド](../windows/eventtargetarray-begin-method.md)|イベント ハンドラーの内部配列の最初の要素のアドレスを取得します。|  
|[EventTargetArray::End メソッド](../windows/eventtargetarray-end-method.md)|イベント ハンドラーの内部配列の最後の要素のアドレスを取得します。|  
|[EventTargetArray::Length メソッド](../windows/eventtargetarray-length-method.md)|イベント ハンドラーの内部配列の要素の現在の数を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `EventTargetArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)