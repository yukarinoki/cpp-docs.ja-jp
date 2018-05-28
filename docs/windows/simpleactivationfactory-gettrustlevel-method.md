---
title: Simpleactivationfactory::gettrustlevel メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b08ce574a8370eb0029a702f8fa4a4b12c6e93c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>SimpleActivationFactory::GetTrustLevel メソッド
によって指定されたクラスのインスタンスの信頼レベルを取得、`Base`クラス テンプレート パラメーター。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `trustLvl`  
 この操作の完了時、現在のクラス オブジェクトの信頼レベル。  
  
## <a name="return-value"></a>戻り値  
 常に S_OK です。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [SimpleActivationFactory クラス](../windows/simpleactivationfactory-class.md)