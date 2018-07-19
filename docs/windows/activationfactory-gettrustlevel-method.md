---
title: Activationfactory::gettrustlevel メソッド |Microsoft ドキュメント
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e4dfbfbc146663722eba1302b27e96812d684f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/08/2018
ms.locfileid: "33854390"
---
# <a name="activationfactorygettrustlevel-method"></a>ActivationFactory::GetTrustLevel メソッド
現在の ActivationFactory がインスタンス化するオブジェクトの信頼レベルを取得します。  
  
## <a name="syntax"></a>構文  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>パラメーター  
 `trustLvl`  
 この操作の完了時、ActivationFactory がインスタンス化するランタイム クラスの信頼レベル。  
  
## <a name="return-value"></a>戻り値  
 正常終了した場合は S_OK、それ以外の場合、アサーション エラーが生成されますと`trustLvl`FullTrust に設定されています。  
  
## <a name="requirements"></a>要件  
 **ヘッダー:** module.h  
  
 **名前空間:** Microsoft::WRL  
  
## <a name="see-also"></a>関連項目  
 [ActivationFactory クラス](../windows/activationfactory-class.md)