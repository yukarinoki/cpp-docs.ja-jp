---
title: Activationfactory::getiids メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetIids
dev_langs:
- C++
helpviewer_keywords:
- GetIids method
ms.assetid: 0983d709-d155-4d65-aae4-5b2c8bb0fede
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6f411f3b2f9e777a4e458b64176ace77a8d13e86
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33855511"
---
# <a name="activationfactorygetiids-method"></a>ActivationFactory::GetIids メソッド
実装されたインターフェイス Id の配列を取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetIids  
)(_Out_ ULONG *iidCount, _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `iidCount`  
 この操作の完了時、interace Id の数、`iids`配列。  
  
 `iids`  
 この操作が完了したらの配列には、インターフェイス Id が実装されています。  
  
## <a name="return-value"></a>戻り値  
 成功した場合は S_OK、そうでない場合は失敗を示す HRESULT。 E_OUTOFMEMORY は、考えられるエラーの HRESULT です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ActivationFactory クラス](../windows/activationfactory-class.md)