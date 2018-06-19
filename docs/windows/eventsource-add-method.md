---
title: Eventsource::add メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::EventSource::Add
dev_langs:
- C++
helpviewer_keywords:
- Add method
ms.assetid: 8bded85b-929e-4425-a464-e5de67bb774c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 92af8746b4d2b5ba2f379cc8660b5345b2c5f175
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33873239"
---
# <a name="eventsourceadd-method"></a>EventSource::Add メソッド
現在の EventSource オブジェクトのイベント ハンドラーのセットを指定したデリゲート インターフェイスによって表されるイベント ハンドラーを追加します。  
  
## <a name="syntax"></a>構文  
  
```  
HRESULT Add(  
   _In_ TDelegateInterface* delegateInterface,  
   _Out_ EventRegistrationToken* token  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `delegateInterface`  
 インターフェイス、デリゲート オブジェクト、イベント ハンドラーを表します。  
  
 `token`  
 この操作の完了時、イベントを表すハンドル。 パラメーターとしてこのトークンを使用して、 [Remove()](../windows/eventsource-remove-method.md)メソッドをイベント ハンドラーを破棄します。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合はエラーを示す HRESULT。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** event.h  
  
 **名前空間:** Microsoft::WRL
 
 ## <a name="see-also"></a>関連項目
 [EventSource クラス](../windows/eventsource-class.md)