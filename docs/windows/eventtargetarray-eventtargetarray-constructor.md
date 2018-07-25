---
title: Eventtargetarray::eventtargetarray コンス トラクター |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fbfd12ea513044f1062e60f5c73f5089683f043d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872716"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>EventTargetArray::EventTargetArray コンストラクター
WRL インフラストラクチャをサポートし、コードから直接使用するものではありません。  
  
## <a name="syntax"></a>構文  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `hr`  
 このコンス トラクター操作後にパラメーター`hr`配列の割り当てが成功したか失敗するかどうかを示します。 次の表に、可能な値`hr`です。  
  
 S_OK  
 操作が成功しました。  
  
 E_OUTOFMEMORY  
 配列のメモリを割り当てられませんでした。  
  
 S_FALSE  
 パラメーター`items`が 0 未満です。  
  
 `items`  
 割り当てる配列要素の数。  
  
## <a name="remarks"></a>コメント  
 EventTargetArray クラスの新しいインスタンスを初期化します。  
  
 EventTargetArray は EventSource オブジェクトでイベント ハンドラーの配列を保持するために使用します。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>関連項目  
 [EventTargetArray クラス](../windows/eventtargetarray-class.md)   
 [Microsoft::WRL::Details 名前空間](../windows/microsoft-wrl-details-namespace.md)