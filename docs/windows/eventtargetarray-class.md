---
title: EventTargetArray クラス |Microsoft ドキュメント
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
ms.openlocfilehash: 4461004a1681d9095449c51fb9cb3973d5017693
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="eventtargetarray-class"></a>EventTargetArray クラス
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>コメント  
 イベント ハンドラーの配列を表します。  
  
 イベント ハンドラーに関連付けられている、 [EventSource](../windows/eventsource-class.md)プロテクト EventTargetArray データ メンバーにオブジェクトが格納されています。  
  
## <a name="members"></a>メンバー  
  
### <a name="public-constructors"></a>パブリック コンストラクター  
  
|名前|説明|  
|----------|-----------------|  
|[EventTargetArray::EventTargetArray コンストラクター](../windows/eventtargetarray-eventtargetarray-constructor.md)|EventTargetArray クラスの新しいインスタンスを初期化します。|  
|[EventTargetArray::~EventTargetArray デストラクター](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|現在の EventTargetArray クラスの初期化を解除します。|  
  
### <a name="public-methods"></a>パブリック メソッド  
  
|名前|説明|  
|----------|-----------------|  
|[EventTargetArray::AddTail メソッド](../windows/eventtargetarray-addtail-method.md)|イベント ハンドラーの内部配列の末尾に指定されたイベント ハンドラーを追加します。|  
|[EventTargetArray::Begin メソッド](../windows/eventtargetarray-begin-method.md)|イベント ハンドラーの内部配列内の最初の要素のアドレスを取得します。|  
|[EventTargetArray::End メソッド](../windows/eventtargetarray-end-method.md)|イベント ハンドラーの内部配列内の最後の要素のアドレスを取得します。|  
|[EventTargetArray::Length メソッド](../windows/eventtargetarray-length-method.md)|イベント ハンドラーの内部配列内の現在の要素数を取得します。|  
  
## <a name="inheritance-hierarchy"></a>継承階層  
 `EventTargetArray`  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)