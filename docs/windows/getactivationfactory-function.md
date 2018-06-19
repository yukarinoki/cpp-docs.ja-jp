---
title: GetActivationFactory 関数 |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f1a4bf31ff44c74362e21e8888630273fcc049e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881339"
---
# <a name="getactivationfactory-function"></a>GetActivationFactory 関数
テンプレート パラメーターによって指定された型の対応するアクティベーション ファクトリを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `T`  
 アクティベーション ファクトリの種類を指定するテンプレート パラメーター。  
  
 `activatableClassId`  
 アクティベーション ファクトリを作成できるクラスの名前。  
  
 `factory`  
 この操作の完了時、アクティベーション ファクトリの種類への参照を`T`です。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、この操作が失敗した理由を示す HRESULT エラーです。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** client.h  
  
 **Namespace:** windows::foundation  
  
## <a name="see-also"></a>関連項目  
 [Windows::Foundation 名前空間](../windows/windows-foundation-namespace.md)