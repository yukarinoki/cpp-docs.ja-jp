---
title: Eventsource::remove メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Remove
dev_langs:
- C++
helpviewer_keywords:
- Remove method
ms.assetid: afafedf5-3665-4408-a639-fb6884f7c5f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: bbf0480252fca342b8a690e93f92ae14ca5e84c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33874383"
---
# <a name="eventsourceremove-method"></a>EventSource::Remove メソッド
現在の EventSource オブジェクトに関連付けられているイベント ハンドラーのセットから指定したイベント登録トークンによって表されるイベント ハンドラーを削除します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Remove(  
   EventRegistrationToken token  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `token`  
 イベント ハンドラーを表すためのハンドル。 イベント ハンドラーがによって登録されたときにこのトークンが返された、 [Add()](../windows/eventsource-add-method.md)メソッドです。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="remarks"></a>コメント  
 EventRegistrationToken 構造体の詳細については、Windows ランタイムのリファレンス ドキュメントで Windows::Foundation::EventRegistrationToken 構造体を参照してください。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [EventSource クラス](../windows/eventsource-class.md)